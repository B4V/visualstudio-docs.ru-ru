---
title: Практическое руководство. Создание адаптера диагностических данных в Visual Studio | Документы Майкрософт
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter, creating
ms.assetid: bd7ad36c-54cb-4d2a-9aea-9d10ad98d7ba
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 82dbe80529fda8dfa599788766823665e4bee0bb
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-diagnostic-data-adapter"></a>Практическое руководство. Создание адаптера диагностических данных

Чтобы создать *адаптер диагностических данных*, нужно создать библиотеку классов с помощью Visual Studio и добавить в нее интерфейсы API адаптера диагностических данных, входящие в Visual Studio Enterprise. Любые необходимые данные можно отправить в <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> инфраструктуры в виде потока или файла при обработке событий, возникших во время тестового запуска. Потоки или файлы, отправляемые в объект <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>, при окончании теста сохраняются в виде вложений в результатах теста. При создании ошибки на основе этих результатов теста и при использовании [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)] эти файлы также связываются с ошибкой.

 Можно создать адаптер диагностических данных, влияющий на компьютер, на котором выполняются тесты, или на компьютер, являющийся частью среды, в которой выполняется тестируемое приложение. Например, он может выполнять сбор файлов на тестовом компьютере (на котором выполняются тесты) или на компьютере, выполняющем роль веб-сервера для приложения.

 Адаптеру диагностических данных можно присвоить понятное имя, которое отображается при создании параметров тестирования в Microsoft Test Manager или Visual Studio. Параметры тестирования позволяют указать роль компьютера, которая будет запускать в среде определенные адаптеры диагностических данных при выполнении тестов. Адаптеры диагностических данных также можно настроить при создании параметров тестирования. Например, можно создать адаптер диагностических данных, собирающий пользовательские журналы с веб-сервера. При создании параметров тестирования можно указать, чтобы этот адаптер диагностических данных запускался на одном или нескольких компьютерах, исполняющих роль веб-сервера, и изменить конфигурацию параметров тестирования для сбора лишь трех журналов, создававшихся последними. Дополнительные сведения о параметрах тестирования см. в статье [Сбор диагностических данных с помощью параметров тестирования](../test/collect-diagnostic-information-using-test-settings.md).

 При выполнении тестов создаются события, чтобы адаптер диагностических данных мог выполнять задачи в этих точках теста.

> [!IMPORTANT]
> Эти события могут возникать на различных потоках (в особенности при выполнении тестов на нескольких компьютерах). Таким образом, необходимо знать о вероятности возникновения проблем в связи с потоками, чтобы случайно не повредить внутренние данные настраиваемого адаптера. Убедитесь в потокобезопасности адаптера диагностических данных.

 Далее перечислены некоторые ключевые события, которые можно использовать при создании адаптера диагностических данных. Полный список событий адаптера диагностических данных см. в абстрактном классе <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>.

|событие|Описание:|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionStart>|Начало тестового запуска|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionEnd>|Завершение тестового запуска|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseStart>|Начало каждого теста в тестовом запуске|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseEnd>|Завершение каждого теста в тестовом запуске|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepStart>|Начало каждого шага теста|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepEnd>|Окончание каждого шага теста|

> [!NOTE]
> При завершении ручного теста прекращается отправка событий сбора данных в адаптер диагностических данных. Повторно выполняемый тест получает новый идентификатор тестового случая. Если пользователь сбрасывает тест в ходе выполнения теста (что вызывает событие <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseReset>) или изменяет результат шага теста, отправка событий сбора данных адаптеру диагностических данных не производится, но идентификатор тестового случая не изменяется. Чтобы определить, выполнялся ли сброс тестового случая, необходимо отследить идентификатор тестового случая в адаптере диагностических данных.

 Чтобы создать адаптер диагностических данных, собирающий данные в файл на основе информации, заданной при создании параметров тестирования, выполните следующие действия.

 Полный пример проекта адаптера диагностических данных, включая специализированный редактор конфигурации, см. в разделе [Пример проекта для создания адаптера диагностических данных](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

##  <a name="CreateAdapter"></a> Создание и установка адаптера диагностических данных

#### <a name="to-create-and-install-a-diagnostic-data-adapter"></a>Создание и установка адаптера диагностических данных

1.  Создайте новую библиотеку классов.

    1.  В меню **Файл** последовательно выберите команды **Создать** и **Создать проект**.

    2.  В разделе **Типы проектов** выберите используемый язык.

    3.  В разделе **Установленные шаблоны Visual Studio** выберите **Библиотека классов**.

    4.  Введите имя адаптера диагностических данных.

    5.  Нажмите кнопку **ОК**.

2.  Добавьте сборку **Microsoft.VisualStudio.QualityTools.ExecutionCommon**.

    1.  В обозревателе решений щелкните правой кнопкой мыши пункт **Ссылки** и выберите команду **Добавить ссылку**.

    2.  Выберите **.NET** и найдите **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

    3.  Нажмите кнопку **ОК**.

3.  Добавьте сборку **Microsoft.VisualStudio.QualityTools.Common**.

    1.  В обозревателе решений щелкните правой кнопкой мыши папку **Ссылки** и выберите команду **Добавить ссылку**.

    2.  Выберите **/.NET** и найдите **Microsoft.VisualStudio.QualityTools.Common.dll**.

    3.  Нажмите кнопку **ОК**.

4.  Добавьте в класс файла следующие выражения с оператором `using`:

    ```csharp
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    using System.Linq;
    using System.Text;
    using System.Xml;
    using System;
    ```

5.  Добавьте <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute> в класс адаптера диагностических данных, чтобы он определялся как адаптер диагностических данных, заменив параметры **Организация**, **Продукт** и **Версия** соответствующими сведениями об этом адаптере диагностических данных:

    ```
    [DataCollectorTypeUri("datacollector://Company/Product/Version")]
    ```

6.  Добавьте в класс атрибут <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>, заменив параметры соответствующими сведениями об этом адаптере диагностических данных.

    ```
    [DataCollectorFriendlyName("Collect Log Files", false)]
    ```

     Это понятное имя будет отображаться в действии параметров тестирования.

    > [!NOTE]
    > Можно также добавить атрибут <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>, чтобы указать тип `Type` пользовательского редактора конфигураций для этого адаптера данных, а также при необходимости задать файл справки, используемый для редактора.
    >
    > Кроме того, можно применить атрибут <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute>, указав тем самым, что адаптер должен быть всегда включен.

7.  Класс создаваемого адаптера диагностических данных должен быть унаследован от класса <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector> следующим образом:

    ```csharp
    public class MyDiagnosticDataAdapter : DataCollector
    ```

8.  Добавление локальных переменных производится следующим образом.

    ```csharp
    private DataCollectionEvents dataEvents;
    private DataCollectionLogger dataLogger;
    private DataCollectionSink dataSink;
    private XmlElement configurationSettings;
    ```

9. Добавьте методы <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector.Initialize*> и **Dispose**. С помощью метода `Initialize` можно инициализировать приемник данных и любые данные конфигурации из параметров тестирования, а также регистрировать требуемые обработчики событий. Это делается следующим образом.

    ```csharp
    public override void Initialize(
        XmlElement configurationElement,
        DataCollectionEvents events,
        DataCollectionSink sink,
        DataCollectionLogger logger,
        DataCollectionEnvironmentContext environmentContext)
    {
           dataEvents = events;  // The test events
           dataLogger = logger;  // The error and warning log
           dataSink = sink;      // Saves collected data
           // Configuration from the test settings
           configurationSettings = configurationElement;

           // Register common events for the data collector
           // Not all of the events are used in this class
        dataEvents.SessionStart +=
            new EventHandler<SessionStartEventArgs>(OnSessionStart);
        dataEvents.SessionEnd +=
            new EventHandler<SessionEndEventArgs>(OnSessionEnd);
        dataEvents.TestCaseStart +=
            new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
        dataEvents.TestCaseEnd +=
            new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
    }

    public override void Dispose(bool disposing)
    {
        if (disposing)
        {
            // Unregister the registered events
            dataEvents.SessionStart -=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd -=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart -=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd -=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
        }
    }
    ```

10. Для получения файла журнала, созданного во время выполнения теста, используйте следующий код обработчика событий и закрытый метод:

    ```csharp
    public void OnTestCaseEnd(sender, TestCaseEndEventArgs e)
    {
        // Get any files to be collected that are
        // configured in your test settings
        List<string> files = getFilesToCollect();

        // For each of the files, send the file to the data sink
        // which will attach it to the test results or to a bug
        foreach (string file in files)
        {
            dataSink.SendFileAsync(e.Context, file, false);
        }
    }

    // A private method that returns the file names
    private List<string> getFilesToCollect()
    {
        // Get a namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                configurationSettings.OwnerDocument.NameTable);
        nsmgr.AddNamespace("ns",
            "http://MyCompany/schemas/MyDataCollector/1.0");

        // Find all of the "File" elements under our configuration
        XmlNodeList files =
            configurationSettings.SelectNodes(
                "//ns:MyDataCollector/ns:File");

        // Build the list of files to collect from the
        // "FullPath" attributes of the "File" nodes.
        List<string> result = new List<string>();
        foreach (XmlNode fileNode in files)
        {
            XmlAttribute pathAttribute =
                fileNode.Attributes["FullPath"];
            if (pathAttribute != null &&
                !String.IsNullOrEmpty(pathAttribute.Value))
            {
                result.Add(pathAttribute.Value);
            }
        }

        return result;
    }
    ```

     Эти файлы вложены в результаты теста. Если при создании ошибки на основе результатов теста используется [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)], эти файлы также добавляются к ошибке.

     Если вы хотите использовать собственный редактор для сбора данных, используемых в параметрах тестирования, см. раздел [Практическое руководство. Создание специализированного редактора данных для адаптера диагностических данных](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

11. Для сбора файла журнала при завершении теста на основе пользовательской настройки параметров тестирования необходимо создать файл `App.config` и добавить его в решение. Этот файл, имеющий следующий формат, должен содержать URI для адаптера диагностических данных для его идентификации. Вместо параметров "Company/ProductName/Version" вставьте реальные значения.

    > [!NOTE]
    > Если не требуется настраивать сведения для адаптера диагностических данных, создавать файл конфигурации не нужно.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <configSections>
        <section name="DataCollectorConfiguration" type="Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationSection, Microsoft.VisualStudio.QualityTools.ExecutionCommon, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a "/>
      </configSections>
      <DataCollectorConfiguration xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/2010">
        <DataCollector typeUri="datacollector://MyCompany/MyProduct/1.0">
          <DefaultConfiguration>
            <!-- Your default config settings -->
            <Binaries>
              <Binary FullPath="C:\Example\Example.dll"/>
              <Binary FullPath="\\Server2\Example2.dll"/>
            </Binaries>
            <Symbols>
              <Symbol FullPath="\\ExampleServer\ExampleSymbol.pdb"/>
            </Symbols>
          </DefaultConfiguration>
        </DataCollector>
      </DataCollectorConfiguration>
    </configuration>
    ```

    > [!NOTE]
    > Элемент конфигурации по умолчанию может содержать любые необходимые данные. Если пользователь не настраивает адаптер диагностических данных в параметрах тестирования, при выполнении адаптера диагностических данных ему будут передаваться данные по умолчанию. Поскольку XML-код, добавляемый в раздел `<DefaultConfigurations>`, скорее всего, не является частью объявленной схемы, можно пропустить все создаваемые им ошибки XML.
    >
    > В следующей папке имеются другие примеры файлов конфигурации в зависимости от каталога установки: **Program Files\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\DataCollectors**.

     Дополнительные сведения о том, как настраивать параметры тестирования для использования среды при выполнении тестов, см. в разделе [Сбор данных диагностики в ручных тестах (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

     Дополнительные сведения об установке файла конфигурации см. в разделе [Практическое руководство. Установка настраиваемого адаптера диагностических данных](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

12. Выполните построение решения для создания сборки адаптера диагностических данных.

13. Дополнительные сведения об установке собственного редактора см. в разделе [Практическое руководство. Установка настраиваемого адаптера диагностических данных](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

14. Дополнительные сведения о том, как настраивать параметры тестирования для использования среды при выполнении тестов, см. в разделе [Сбор данных диагностики в ручных тестах (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

15. Чтобы выбрать адаптер диагностических данных, нужно выбрать существующие параметры тестирования или создать новый параметр с помощью Microsoft Test Manager или Visual Studio. Адаптер отображается на вкладке **Данные и диагностика** параметров тестирования и имеет понятное имя, присвоенное классу.

16. Сделайте эти параметры теста активными. Дополнительные сведения о параметрах тестирования см. в статье [Сбор диагностических данных с помощью параметров тестирования](../test/collect-diagnostic-information-using-test-settings.md).

17. Выполните тесты с данными параметрами тестирования, выбрав свой адаптер диагностических данных.

   Указанный файл данных присоединяется к результатам тестов.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute>
- [Сбор диагностических данных с помощью параметров тестирования](../test/collect-diagnostic-information-using-test-settings.md)
- [Сбор данных диагностики в ручных тестах (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Сбор диагностических данных во время тестирования (VSTS)](/vsts/manual-test/collect-diagnostic-data)
- [Практическое руководство. Создание специализированного редактора данных для адаптера диагностических данных](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)