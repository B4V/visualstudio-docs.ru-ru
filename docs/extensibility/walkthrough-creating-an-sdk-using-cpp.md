---
title: "Пошаговое руководство: Создание пакета SDK с помощью C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36ea793b-3832-41a1-b906-69e680ad5e1d
caps.latest.revision: 32
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: d4458cb2cf0f3f198b2931beec15f8eead446ba6
ms.openlocfilehash: 3baf914755f0cdd4e0aa0a6c1405126faeec0364
ms.lasthandoff: 02/22/2017

---
# <a name="walkthrough-creating-an-sdk-using-c"></a>Пошаговое руководство: Создание пакета SDK с помощью C++
В этом пошаговом руководстве демонстрируется создание собственного математические библиотеки C++ SDK, пакет SDK в Visual Studio расширения (VSIX), а затем использовать его для создания приложения. Пошаговое руководство состоит из следующие действия:  
  
-   [Чтобы создать машинный код и библиотеки среды выполнения Windows](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createClassLibrary)  
  
-   [Создание проекта расширения NativeMathVSIX](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createVSIX)  
  
-   [Создание примера приложения, использующего библиотеку классов](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createSample)  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Дополнительные сведения см. в разделе [пакет SDK для Visual Studio](../extensibility/visual-studio-sdk.md).  
  
##  <a name="a-namecreateclasslibrarya-to-create-the-native-and-windows-runtime-libraries"></a><a name="createClassLibrary"></a>Чтобы создать машинный код и библиотеки среды выполнения Windows  
  
1.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
2.  В списке шаблонов разверните **Visual C++**, **магазина Windows**, а затем выберите **DLL (приложения для магазина Windows)** шаблона. В **имя** укажите `NativeMath`, а затем выберите **ОК** кнопки.  
  
3.  Обновите NativeMath.h в соответствии со следующими кодом.  
  
     [!code-cpp[CreatingAnSDKUsingCpp&#1;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_1.h)]  
  
4.  Обновление NativeMath.cpp для сопоставления этого кода:  
  
     [!code-cpp[CreatingAnSDKUsingCpp&#2;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_2.cpp)]  
  
5.  В **обозревателе решений**, откройте контекстное меню для **решение «NativeMath»**и нажмите кнопку **добавить**, **новый проект**.  
  
6.  В списке шаблонов разверните **Visual C++**, а затем выберите **компонента среды выполнения Windows** шаблона. В **имя** укажите `NativeMathWRT`, а затем выберите **ОК** кнопки.  
  
7.  Обновление Class1.h для сопоставления этого кода:  
  
     [!code-cpp[CreatingAnSDKUsingCpp&#3;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_3.h)]  
  
8.  Обновление Class1.cpp для сопоставления этого кода:  
  
     [!code-cpp[CreatingAnSDKUsingCpp&#4;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_4.cpp)]  
  
9. В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
##  <a name="a-namecreatevsixa-to-create-the-nativemathvsix-extension-project"></a><a name="createVSIX"></a>Создание проекта расширения NativeMathVSIX  
  
1.  В **обозревателе решений**, откройте контекстное меню для **решение «NativeMath»**и нажмите кнопку **добавить**, **новый проект**.  
  
2.  В списке шаблонов разверните **Visual C#**, **расширения**, а затем выберите **пакет VSIX**. В **имя** укажите **NativeMathVSIX**, а затем выберите **ОК** кнопки.  
  
3.  Когда откроется конструктор манифеста VSIX, закройте ее.  
  
4.  В **обозревателе решений**, откройте контекстное меню для **source.extension.vsixmanifest**, а затем выберите **Просмотр кода**.  
  
5.  Используйте следующий XML-код для замены существующих XML.  
  
    [!code-xml[CreatingAnSDKUsingCpp №&6;](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_6.xml)]

6.  В **обозревателе решений**, откройте контекстное меню для **NativeMathVSIX** проекта, а затем выберите **добавить**, **новый элемент**.  
  
7.  В списке **элементы Visual C#**, разверните **данные**, а затем выберите **XML-файл**. В **имя** укажите `SDKManifest.xml`, а затем выберите **ОК** кнопки.  
  
8.  Замените содержимое файла, используйте этот XML-код:  
  
     [!code-xml[CreatingAnSDKUsingCpp&#5;](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_5.xml)]  
  
9. В **обозревателе решений**в **NativeMathVSIX** проект, создайте следующую структуру папок:  
  
    ```  
  
    \DesignTime  
          \CommonConfiguration  
                \Neutral  
                      \Include  
          \Debug  
                \x86  
    \Redist  
          \Debug  
                \x86  
    \References  
          \CommonConfiguration  
                \Neutral  
    ```  
  
10. В **обозреватель решений**, откройте контекстное меню для **решение «NativeMath»**, а затем выберите **открыть папку в проводнике**.  
  
11. В **проводнике**, скопируйте \NativeMath\NativeMath.h и затем в **обозревателе решений**в **NativeMathVSIX** проекта, вставьте его в папке \DesignTime\CommonConfiguration\Neutral\Include\.  
  
     \Debug\NativeMath\NativeMath.lib скопируйте и вставьте его в папке \DesignTime\Debug\x86\.  
  
     \Debug\NativeMath\NativeMath.dll скопируйте и вставьте его в папке \Redist\Debug\x86\.  
  
     DebugNativeMathWRTNativeMathWRT.dll скопируйте и вставьте его в папке RedistDebugx86.  
  
     DebugNativeMathWRTNativeMathWRT.winmd скопируйте и вставьте его в папке ReferencesCommonConfigurationNeutral.  
  
     DebugNativeMathWRTNativeMathWRT.pri скопируйте и вставьте его в папке ReferencesCommonConfigurationNeutral.  
  
12. В папке \DesignTime\Debug\x86\ создайте текстовый файл с именем NativeMathSDK.props и вставьте в него следующее содержимое:  
  
    [!code-xml[CreatingAnSDKUsingCpp&#7;](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_7.xml)]  
  
13. В строке меню выберите **представление**, **другие окна**, **окно свойств** (Клавиатура: нажмите клавишу F4).  
  
14. В **обозревателе решений**выберите **NativeMathWRT.winmd** файла. В **свойства** измените **действие при построении** свойства **содержимого**и затем измените **включить в VSIX** свойства **True**.  
  
     Повторите эту процедуру для **SimpleMath.pri** файла.  
  
     Повторите эту процедуру для **NativeMath.Lib** файла.  
  
     Повторите эту процедуру для **NativeMathSDK.props** файла.  
  
15. В **обозревателе решений**выберите **NativeMath.h** файла. В **свойства** измените **включить в VSIX** свойства **True**.  
  
     Повторите эту процедуру для **NativeMath.dll** файла.  
  
     Повторите эту процедуру для **NativeMathWRT.dll** файла.  
  
     Повторите эту процедуру для **SDKManifest.xml** файла.  
  
16. В строке меню последовательно выберите **Сборка**и **Собрать решение**.  
  
17. В **обозревателе решений**, откройте контекстное меню для **NativeMathVSIX** проекта, а затем выберите **открыть папку в проводнике**.  
  
18. В **проводнике**, перейдите в папку \bin\Debug\ и запустить NativeMathVSIX.vsix, чтобы начать установку.  
  
19. Выберите **установить** кнопку и дождитесь завершения установки перезапустите Visual Studio.  
  
##  <a name="a-namecreatesamplea-to-create-a-sample-app-that-uses-the-class-library"></a><a name="createSample"></a>Создание примера приложения, использующего библиотеку классов  
  
1.  В строке меню выберите **Файл**, **Создать**, **Проект**.  
  
2.  В списке шаблонов разверните **Visual C++**, **магазина Windows**, а затем выберите **пустое приложение**. В **имя** укажите **NativeMathSDKSample**, а затем выберите **ОК** кнопки.  
  
3.  В **обозревателе решений**, откройте контекстное меню для **NativeMathSDKSample** проекта, а затем выберите **добавить**, **ссылка**.  
  
4.  На **общие свойства**, **.NET Framework и ссылки** на странице свойств в списке ссылочных типов, разверните **Windows**и выберите **расширения**. В области сведений выберите **собственного пакета SDK математические** расширения и нажмите кнопку **добавить новую ссылку** кнопки.  
  
5.  В **добавить ссылку** диалоговом **собственного пакета SDK математические** флажок, а затем выберите **ОК** кнопки.  
  
6.  Отображает свойства проекта для NativeMathSDKSample.  
  
     Свойства, определенные в NativeMathSDK.props были применены при добавлении ссылки. Это можно проверить с помощью проверки **каталоги VC ++** свойства в проекте **свойства конфигурации**.  
  
7.  В **обозревателе**, откройте файл MainPage.xaml и выполните следующий код XAML, чтобы заменить его содержимое:  
  
     [!code-xml[CreatingAnSDKUsingCppDemoApp&#1;](../extensibility/codesnippet/Xaml/walkthrough-creating-an-sdk-using-cpp_8.xaml)]  
  
8.  Обновление Mainpage.xaml.h для сопоставления этого кода:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp&#2;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_9.h)]  
  
9. Обновление MainPage.xaml.cpp для сопоставления этого кода:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp&#3;](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_10.cpp)]  
  
10. Нажмите клавишу F5, чтобы запустить приложение.  
  
11. В приложении введите любых двух чисел, выберите операцию и нажмите кнопку ** = ** кнопки.  
  
     Отображается правильный результат.  
  
 В этом пошаговом руководстве показано, как создать и использовать пакет SDK расширения для вызова [!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] библиотеки и не -[!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] библиотеки.  
  
## <a name="next-steps"></a>Дальнейшие действия  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Создание пакета SDK с помощью C# или Visual Basic](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [Создание средств разработки программного обеспечения](../extensibility/creating-a-software-development-kit.md)