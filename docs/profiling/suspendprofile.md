---
title: "SuspendProfile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SuspendProfile"
ms.assetid: 7c8de6e6-bb88-4353-92c3-ce7290310d61
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# SuspendProfile
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Метод `SuspendProfile` увеличивает на единицу значение счетчика приостановки\/возобновления для указанного уровня профилирования.  
  
## Синтаксис  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI SuspendProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### Параметры  
 `Level`  
  
 Указывает уровень профилирования, к которому можно применить сбор данных о производительности.  Для указания одного из трех уровней, к которому можно применить сбор данных о производительности, следует использовать следующие перечислители **PROFILE\_CONTROL\_LEVEL**.  
  
|Enumerator|Описание|  
|----------------|--------------|  
|PROFILE\_GLOBALLEVEL|Установка глобального уровня оказывает влияние на все процессы и потоки при выполнении профилирования.|  
|PROFILE\_PROCESSLEVEL|Установка уровня процесса оказывает влияние на все потоки, являющиеся частью указанного процесса.|  
|PROFILE\_THREADLEVEL|Установка уровня профилирования потока влияет на заданный поток.|  
  
 `dwId`  
  
 Идентификатор процесса или потока, созданный системой.  
  
## Значение свойства, возвращаемое значение  
 Функция указывает на успешное выполнение или сбой посредством перечисления **PROFILE\_COMMAND\_STATUS**.  Ниже перечислены возможные возвращаемые значения.  
  
|Enumerator|Описание|  
|----------------|--------------|  
|PROFILE\_ERROR\_ID\_NOEXIST|Идентификатор элемента профилирования не существует.|  
|PROFILE\_ERROR\_LEVEL\_NOEXIST|Заданный уровень профилирования не существует.|  
|PROFILE\_ERROR\_MODE\_NEVER|При вызове функции для режима профилирования было задано значение NEVER.|  
|PROFILE\_ERROR\_NOT\_YET\_IMPLEMENTED|Вызов функции профилирования, уровень профилирования или сочетание вызова и уровня пока не реализованы.|  
|PROFILE\_OK|Вызов выполнен успешно.|  
  
## Заметки  
 Начальное значение счетчика приостановки\/возобновления равно 0.  Каждый вызов SuspendProfile добавляет 1 к счетчику приостановки\/возобновления; каждый вызов ResumeProfile вычитает 1.  
  
 Если значение счетчика Пауза\/Возобновление больше 0, состояние Пауза\/Возобновление для уровня выключено.  Если значение счетчика больше или равно 0, состояние Пауза\/Возобновление включено.  
  
 Если Пуск\/Остановка, и Пауза\/Возобновление включены, состояние профилирования для данного уровня включено.\<\/para\>  Для профилируемого потока состояния глобального уровня, уровня процесса и потока должны быть равны значению ON.  
  
## Эквивалент в .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## Сведения о функции  
 Заголовок: объявлен в файле VSPerf.h.  
  
 Импортируемая библиотека: VSPerf.lib  
  
## Пример  
 В следующем примере демонстрируется использование метода SuspendProfile.  В примере предполагается, что для процесса или потока, определенного параметром [PROFILE\_CURRENTID](../profiling/profile-currentid.md), предварительно выполнен вызов метода StartProfile.  
  
```  
void ExerciseSuspendProfile()  
{  
    // The initial value of the Suspend/Resume counter is 0.  
    // Each call to SuspendProfile adds 1 to the  
    // Suspend/Resume count; each call  
    // to ResumeProfile subtracts 1.  
  
    // Variables used to print output  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call  
    // to SuspendProfile  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = SuspendProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("SuspendProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## См. также  
 [Справочник по API\-интерфейсам профилировщика Visual Studio \(машинный код\)](../profiling/visual-studio-profiler-api-reference-native.md)