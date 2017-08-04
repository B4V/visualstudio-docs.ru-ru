---
title: "Практическое руководство. Указание событий сборки (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-build events
- events [Visual Studio], builds
- post-build events
- build events [Visual Studio]
- builds [Visual Studio], events
ms.assetid: 40dc83bf-a7c5-4a14-816a-fa0980b6e4c3
caps.latest.revision: 26
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 595995a0369ff74c4223e7a585c913bc90aca411
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-specify-build-events-visual-basic"></a>Практическое руководство. Указание событий построения (Visual Basic)
События сборки в Visual Basic можно использовать для выполнения скриптов, макросов или других действий в составе процесса компиляции. События перед сборкой происходят до компиляции; события после сборки происходят после компиляции.  
  
 События сборки указываются в диалоговом окне **События сборки**, которое можно открыть со страницы **Компиляция** **конструктора проектов**.  
  
> [!NOTE]
>  Visual Basic Express не поддерживает запись событий сборки. Она поддерживается только в полных версиях Visual Studio.  
  
## <a name="how-to-specify-pre-build-and-post-build-events"></a>Как указать события перед сборкой и после нее  
  
#### <a name="to-specify-a-build-event"></a>Чтобы указать событие сборки  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  Откройте вкладку **Компиляция**.  
  
3.  Нажмите кнопку **События сборки**, чтобы открыть диалоговое окно **События сборки**.  
  
4.  Введите аргументы командной строки для действий перед сборкой и после нее и нажмите кнопку **ОК**.  
  
    > [!NOTE]
    >  Добавьте оператор `call` перед всеми командами после сборки, запускающими BAT-файлы. Например, `call C:\MyFile.bat` или `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
    > [!NOTE]
    >  Если событие перед сборкой или после сборки завершается ошибкой, можно прервать сборку, задав завершение действия события с кодом, отличным от нуля (0), что означает успешное выполнение действия.  
  
## <a name="example-how-to-change-manifest-information-using-a-post-build-event"></a>Пример: как изменить данные манифеста с помощью события после построения  
 В следующей процедуре демонстрируется, как задать минимальную версию операционной системы в манифесте приложения с помощью команды EXE, вызываемой из события после сборки (файл exe.manifest файл в каталоге проекта). Минимальная версия операционной системы — число из четырех частей, например 4.10.0.0. Чтобы это сделать, команда изменит раздел `<dependentOS>` манифеста:  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### <a name="to-create-an-exe-command-to-change-the-application-manifest"></a>Чтобы создать команду EXE для изменения манифеста приложения  
  
1.  Создайте консольное приложение для команды. В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  В диалоговом окне **Новый проект** в узле **Visual Basic** выберите **Приложение Windows**, а затем шаблон **Консольное приложение**. Задайте для проекта имя `ChangeOSVersionVB`.  
  
3.  В Module1.vb добавьте следующую строку для других инструкций `Imports` в верхней части файла:  
  
    ```  
    Imports System.Xml  
    ```  
  
4.  Добавьте следующий код в `Sub Main`:  
  
    ```  
    Sub Main()  
       Dim applicationManifestPath As String  
       applicationManifestPath = My.Application.CommandLineArgs(0)  
       Console.WriteLine("Application Manifest Path: " & applicationManifestPath.ToString)  
  
       'Get version name  
       Dim osVersion As Version  
       If My.Application.CommandLineArgs.Count >= 2 Then  
          osVersion = New Version(My.Application.CommandLineArgs(1).ToString)  
       Else  
          Throw New ArgumentException("OS Version not specified.")  
       End If  
       Console.WriteLine("Desired OS Version: " & osVersion.ToString())  
  
       Dim document As XmlDocument  
       Dim namespaceManager As XmlNamespaceManager  
       namespaceManager = New XmlNamespaceManager(New NameTable())  
       With namespaceManager  
          .AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1")  
          .AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2")  
       End With  
  
       document = New XmlDocument()  
       document.Load(applicationManifestPath)  
  
       Dim baseXPath As String  
       baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os"  
  
       'Change minimum required OS Version.  
       Dim node As XmlNode  
       node = document.SelectSingleNode(baseXPath, namespaceManager)  
       node.Attributes("majorVersion").Value = osVersion.Major.ToString()  
       node.Attributes("minorVersion").Value = osVersion.Minor.ToString()  
       node.Attributes("buildNumber").Value = osVersion.Build.ToString()  
       node.Attributes("servicePackMajor").Value = osVersion.Revision.ToString()  
  
       document.Save(applicationManifestPath)  
    End Sub  
    ```  
  
     Команда принимает два аргумента. Первый аргумент — это путь к манифесту приложения (то есть папка, в которой в процессе сборки создается манифест, обычно Projectname.publish). Вторым аргументом является новая версия операционной системы.  
  
5.  В меню **Сборка** выберите **Собрать решение**.  
  
6.  Скопируйте EXE-файл в каталог, например `C:\TEMP\ChangeOSVersionVB.exe`.  
  
 Затем вызовите эту команду в событие после сборки для изменения манифеста приложения.  
  
#### <a name="to-invoke-a-post-build-event-to-change-the-application-manifest"></a>Чтобы вызвать событие после сборки для изменения манифеста приложения  
  
1.  Создайте приложение Windows для проекта, который должен быть опубликован. В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  В диалоговом окне **Новый проект** в узле **Visual Basic** выберите **Windows**, а затем шаблон **Приложение Windows**. Задайте для проекта имя `VBWinApp`.  
  
3.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните пункт **Свойства**.  
  
4.  В конструкторе проектов перейдите на страницу **Публикация** и для параметра **Расположение публикации** задайте значение `C:\TEMP\`.  
  
5.  Опубликуйте проект, щелкнув **Опубликовать сейчас**.  
  
     Файл манифеста будет построен и размещен в `C:\TEMP\VBWinApp_1_0_0_0\VBWinApp.exe.manifest`. Чтобы просмотреть манифест, щелкните правой кнопкой мыши файл и выберите пункт **Открыть с помощью**, затем выберите **Выбрать программу из списка** и щелкните **Блокнот**.  
  
     Найдите в файле элемент `<osVersionInfo>`. Например, версия может быть следующей:  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  В конструкторе проектов перейдите на вкладку **Компиляции** и нажмите кнопку **События сборки**, чтобы открыть диалоговое окно **События сборки**.  
  
7.  В **командной строке события после сборки** введите следующую команду:  
  
     `C:\TEMP\ChangeOSVersionVB.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     При сборке проекта выполнение этой команды приведет к изменению минимальной версии операционной системы в манифесте приложения на 5.1.2600.0.  
  
     Макрос `$(TargetPath)` выражает полный путь к создаваемому исполняемому файлу. Поэтому $(TargetPath).manifest будет указывать манифест приложения, созданный в каталоге bin. При публикации этот манифест будет скопирован в расположение публикаций, которое было задано ранее.  
  
8.  Опубликуйте проект еще раз. Откройте страницу **Публикация** и нажмите кнопку **Опубликовать сейчас**.  
  
     Еще раз просмотрите манифест. Чтобы просмотреть манифест, перейдите в каталог публикации, щелкните правой кнопкой мыши файл и выберите пункт **Открыть с помощью**, затем выберите **Выбрать программу из списка** и щелкните **Блокнот**.  
  
     Версия должна иметь следующий вид:  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## <a name="see-also"></a>См. также  
 [Управление свойствами компиляции](http://msdn.microsoft.com/en-us/94308881-f10f-4caf-a729-f1028e596a2c)   
 [Страница "Компиляция" в конструкторе проектов (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Страница "Публикация" в конструкторе проектов](../ide/reference/publish-page-project-designer.md)   
 [Диалоговое окно «Командная строка события "До сборки" или "После сборки"»](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [Практическое руководство. Назначение событий построения (C#)](../ide/how-to-specify-build-events-csharp.md)