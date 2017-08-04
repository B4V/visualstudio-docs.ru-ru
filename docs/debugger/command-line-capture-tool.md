---
title: "Программа командной строки для захвата | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db75b3a7-80b2-4a74-91d2-fd6e0f73b45d
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Программа командной строки для захвата
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

DXCap.exe — это программа командной строки для захвата и воспроизведения данных диагностики графики.  Она поддерживает все функциональные уровни Direct3D версий 10–12.  
  
## Синтаксис  
  
```ms-dos  
DXCap.exe [-file filename] [-frame frames | -period periods | -manual] -c app [args...]  
DXCap.exe -p [filename] [-debug | -warp | -hw] [-config] [-rawmode]  
DXCap.exe –p [filename] –screenshot [-frame frames]  
DXCap.exe –p [filename] –toXML [xml_filename]  
DXCap.exe –v [–file filename] [-examine events] [-haltonfail | -exitonfail] [-showprogress]  
DXCap.exe -e [search_string]  
DXCap.exe –info  
```  
  
#### Параметры  
 `-file` `filename`  
 В режиме захвата \(`-c`\) параметр `filename` определяет имя файла журнала графики, в который записываются графические данные.  Если параметр `filename` не задан, графические данные по умолчанию записываются в файл с именем `<имя_приложения>-<дата>-<время>.vsglog`.  
  
 В режиме проверки \(\-v\) параметр `filename` определяет имя файла журнала графики, который необходимо проверить.  Если параметр `filename` не задан, повторно используется журнал графики, который проверялся в последний раз.  
  
 `-frame` `frames`  
 В режиме захвата параметр `frames` определяет кадры, которые необходимо захватить.  Первый кадр имеет номер 1.  Чтобы указать несколько кадров, можно перечислить их через запятую или использовать диапазоны.  Например, если параметр `frames` имеет значение `2, 5, 7-9, 15`, то захватываются кадры `2`, `5`, `7`, `8`, `9` и `15`.  
  
 `-period` `periods`  
 В режиме захвата параметр `periods` определяет интервал времени \(в секундах\), в течение которого необходимо захватывать кадры.  Чтобы указать несколько периодов, можно перечислить их через запятую или использовать диапазоны.  Например, если параметр `periods` имеет значение `2.1-5, 7.0-9.3`, то захватываются кадры, отрисовываемые в течение интервалов от `2,1` до `5` секунд и от `7` до `9,3` секунд.  
  
 `-manual`  
 В режиме захвата параметр `-manual` указывает на то, что кадры будут захватываться вручную путем нажатия клавиши PRINT SCREEN.  Кадры можно захватывать, когда приложение запущено. Чтобы остановить захват кадров, вернитесь в интерфейс командной строки и нажмите клавишу ВВОД.  
  
 `-c` `app` \[`args...`\]  
 Режим захвата.  В режиме захвата параметр `app` определяет имя приложения, из которого необходимо захватить графические данные. `args...` определяет дополнительные параметры командной строки для этого приложения.  
  
 `-p` \[`filename`\]  
 Режим воспроизведения \(`-p`\).  В режиме воспроизведения параметр `filename` определяет имя файла журнала графики, который необходимо воспроизвести.  Если параметр `filename` не задан, повторно используется журнал графики, который воспроизводился в последний раз.  
  
 `-debug`  
 В режиме воспроизведения параметр `-debug` указывает на то, что воспроизведение должно осуществляться с включенным уровнем отладки Direct3D.  
  
 `-warp`  
 В режиме воспроизведения параметр `-warp` указывает на то, что воспроизведение должно осуществляться с помощью программной отрисовки WARP.  
  
 `-hw`  
 В режиме воспроизведения параметр `-hw` указывает на то, что воспроизведение должно осуществляться с помощью оборудования GPU.  
  
 `-config`  
 В режиме воспроизведения параметр `-config` выводит информацию о компьютере, который использовался для захвата файла журнала графики, если эта информация была записана в журнал.  
  
 `-rawmode`  
 В режиме воспроизведения параметр `-rawmode` указывает на то, что воспроизведение должно осуществляться без изменения записанных событий.  В обычном режиме воспроизведения в воспроизводимые данные могут вноситься небольшие изменения с целью упростить отладку и ускорить воспроизведение.  Например, вместо выполнения команд цепочки буферов выходные данные цепочки буферов могут имитироваться.  Обычно это не создает проблем, но вам может потребоваться более точно воспроизвести записанные события. Например, с помощью этого параметра можно воспроизвести поведение при полноэкранной отрисовке приложения, которое было захвачено в полноэкранном режиме.  
  
 `-toXML` \[`xml_filename`\]  
 В режиме воспроизведения параметр `xml_filename` определяет имя файла, в который записывается XML\-представление воспроизводимых данных.  Если параметр `xml_filename` не задан, XML\-представление записывается в файл, имя которого совпадает с именем воспроизводимого файла, но с расширением `.xml`.  
  
 `-v`  
 Режим проверки.  В режиме проверки захваченные кадры воспроизводятся на оборудовании и в WARP, а результаты сравниваются с помощью функции сравнения изображений.  С помощью этой функции можно быстро выявить проблемы с драйвером, влияющие на отрисовку.  
  
 `-examine` `events`  
 В режиме проверки параметр `events` определяет набор событий графики, непосредственные результаты которых необходимо сравнить.  Например, параметр `-examine present,draw,copy,clear` ограничивает сравниваемые события только теми, которые относятся к указанным категориям.  
  
> [!TIP]
>  Мы рекомендуем начать сравнение с набора `-examine present,draw,copy,clear`, так как при этом будет выявлено большинство проблем, а времени потребуется значительно меньше, чем при сравнении более полного набора событий.  При необходимости вы можете указать другой набор событий для проверки, чтобы выявить другие проблемы.  
  
 `-haltonfail`  
 В режиме проверки параметр `-haltonfail` останавливает проверку при обнаружении различий между аппаратной отрисовкой и отрисовкой WARP.  Проверка возобновляется после нажатия клавиши.  
  
 `-exitonfail`  
 В режиме проверки параметр `-exitonfail` немедленно прерывает проверку при обнаружении различий между аппаратной отрисовкой и отрисовкой WARP.  При выходе из программы таким образом в среду возвращается значение `0`; в противном случае возвращается значение `1`.  
  
 `-showprogress`  
 В режиме проверки параметр `-showprogress` выводит сведения о ходе выполнения сеанса проверки.  Ход отрисовки WARP показан слева, а ход аппаратной отрисовки — справа.  
  
 `-e` `search_string`  
 Перечисление установленных приложений Магазина Windows.  Эту информацию можно использовать для захвата информации из приложений Магазина Windows с помощью командной строки.  
  
 `-info`  
 Выводит информацию о компьютере и библиотеках DLL захвата.  
  
## Примечания  
 Программа DXCap.exe работает в трех режимах.  
  
 Режим захвата \(\-c\)  
 Графические данные захватываются из работающего приложения и записываются в файл журнала графики.  Возможности захвата и формат файла аналогичны используемым в Visual Studio.  
  
 Режим воспроизведения \(\-p\)  
 Воспроизведение ранее захваченных событий графики из существующего файла журнала графики.  По умолчанию воспроизведение осуществляется в окне, даже если файл журнала графики был захвачен из полноэкранного приложения.  Воспроизведение осуществляется в полноэкранном режиме только в том случае, если файл журнала графики был захвачен из полноэкранного приложения и указан параметр `–rawmode`.  
  
 Режим проверки \(`-v`\)  
 Проверка поведения отрисовки путем воспроизведения захваченных кадров на оборудовании и в WARP и последующего сравнения результатов с помощью функции сравнения изображений.  С помощью этой функции можно быстро выявить проблемы с драйвером, влияющие на отрисовку.  
  
 Помимо этих режимов, программа dxcap.exe выполняет еще две функции, которые не предусматривают захват или воспроизведение графических данных.  
  
 Функция перечисления \(`-e`\)  
 Выводит подробные сведения о приложениях Магазина Windows, установленных на компьютере.  Эти сведения включают в себя имя пакета и идентификатор appid, определяющий исполняемый файл приложения Магазина Windows.  Для захвата графических данных из приложения Магазина Windows с помощью программы DXCap.exe используйте имя пакета и идентификатор appid вместо имени исполняемого файла, которое используется при захвате данных из классического приложения.  
  
 Функция вывода информации \(`-info)`  
 Выводит подробные сведения о компьютере и библиотеках DLL захвата.  
  
## Примеры  
  
### Захват графических данных из классического приложения  
 Чтобы указать приложение, из которого нужно захватить графические данные, используйте параметр `–c`.  
  
```ms-dos  
DXCap.exe –c BasicHLSL11.exe  
```  
  
 По умолчанию графические данные записываются в файл с именем `<имя_приложения>-<дата>-<время>.vsglog`.  Чтобы указать другой файл для записи данных, используйте параметр `–file`.  
  
```ms-dos  
DXCap.exe –file regression_test_12.vsglog –c BasicHLSL11.exe  
```  
  
 Чтобы указать дополнительные параметры командной строки для приложения, из которого захватываются данные, добавьте их после имени файла приложения.  
  
```ms-dos  
DXCap.exe –c "C:\Program Files\Internet Explorer\iexplorer.exe" "www.fishgl.com"  
```  
  
 Команда в приведенном выше примере захватывает графические данные из классической версии браузера Internet Explorer во время просмотра веб\-страницы по адресу www.fishgl.com, которая использует API WebGL для отрисовки трехмерного содержимого.  
  
> [!NOTE]
>  Так как аргументы командной строки, находящиеся после имени приложения, передаются в него, аргументы, предназначенные для программы DXCap.exe, необходимо указать перед параметром `–c`.  
  
### Захват графических данных из приложения Магазина Windows  
 Вы можете захватывать графические данные из приложения Магазина Windows.  
  
```ms-dos  
DXCap.exe –c Microsof.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps  
```  
  
 Захват данных из приложения Магазина Windows с помощью программы DXCap.exe осуществляется так же, как из классического приложения Windows, но вместо указания приложения по имени файла приложение Магазина Windows указывается по имени пакета и идентификатору исполняемого файла внутри этого пакета.  Чтобы узнать, как идентифицируются приложения Магазина Windows, установленные на компьютере, используйте программу DXCap.exe с параметром `–e`, чтобы перечислить их.  
  
```ms-dos  
DXCap.exe -e  
```  
  
 Вы можете указать дополнительную строку поиска, чтобы найти конкретное приложение.  Если указана строка поиска, программа DXCap.exe перечисляет приложения Магазина Windows, имена пакетов, имена приложений или идентификаторы приложений которых совпадают со строкой.  При поиске не учитывается регистр.  
  
```ms-dos  
DXCap.exe –e map  
```  
  
 Приведенная выше команда перечисляет приложения Магазина Windows, которые соответствуют строке "map". Ниже приведены результаты ее выполнения.  
  
  **Package "Microsoft.BingMaps":**  
 **InstallDirectory : C:\\Program Files\\WindowsApps\\Microsoft.BingMaps\_2.1.2914.1734\_x64\_\_8wekyb3d8bbwe**  
 **FullName         : Microsoft.BingMaps\_2.1.2914.1734\_x64\_\_8wekyb3d8bbwe**  
 **UserSID          : S\-1\-5\-21\-2127521184\-1604012920\-1887927527\-5603533**  
 **Name             : Microsoft.BingMaps**  
 **Publisher        : CN\=Microsoft Corporation, O\=Microsoft Corporation, L\=Redmond, S\=Washington, C\=US**  
 **Version          : 2.1.2914.1734**  
 **Launchable Applications:**  
 **Id   : AppexMaps**  
 **Exe  : C:\\Program Files\\WindowsApps\\Microsoft.BingMaps\_2.1.2914.1734\_x64\_\_8wekyb3d8bbwe\\Map.exe**  
 **IsWWA: No**  
 **AppSpec \(to launch\): **DXCap.exe \-c Microsoft.BingMaps\_2.1.2914.1734\_x64\_\_8wekyb3d8bbwe,AppexMaps****  В последней строке выходных данных для каждого перечисленного приложения приводится команда, с помощью которой можно захватить графические данные из него.  
  
### Захват определенных кадров или кадров в течение определенного интервала  
 Чтобы указать кадры, которые необходимо захватить, через запятую и с помощью диапазонов, используйте параметр `–frame`.  
  
```ms-dos  
DXCap.exe –frame 2,5,7-9,15 –c SimpleBezier11.exe  
```  
  
 Либо используйте параметр `–period`, чтобы указать набор интервалов времени, в течение которых должны захватываться кадры.  Интервалы времени указываются в секундах; можно задать несколько интервалов.  
  
```ms-dos  
DXCap.exe –period 2.1-5, 7.0-9.3 –c SimpleBezier11.exe  
```  
  
### Захват кадров в интерактивном режиме  
 Для захвата кадров в интерактивном режиме используйте параметр `–manual`.  Чтобы начать захват, нажмите клавишу ВВОД. Чтобы остановить захват, нажмите клавишу ВВОД еще раз.  
  
```ms-dos  
DXCap.exe –manual -c SimpleBezier11.exe  
```  
  
### Воспроизведение файла журнала графики  
 Чтобы воспроизвести ранее захваченный файл журнала графики, используйте параметр `-p`.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog  
```  
  
 Чтобы воспроизвести последний захваченный журнал графики, не указывайте имя файла.  
  
```ms-dos  
DXCap.exe –p  
```  
  
### Воспроизведение в режиме исходных данных  
 Чтобы воспроизвести захваченные команды в исходном виде, используйте параметр `-rawmode`.  В обычном режиме воспроизведения некоторые команды эмулируются. Например, файл журнала графики, захваченный из полноэкранного приложения, будет воспроизводиться в окне. При включении режима исходных данных будет предпринята попытка воспроизведения этого файла в полноэкранном режиме.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog -rawmode  
```  
  
### Воспроизведение с помощью WARP или аппаратного устройства  
 Вам может потребоваться принудительно воспроизвести файл журнала графики, захваченный на аппаратном устройстве, с помощью WARP или принудительно воспроизвести журнал, захваченный в WARP, с помощью аппаратного устройства.  Для воспроизведения с помощью WARP используйте параметр `-warp`.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog -warp  
```  
  
 Для воспроизведения с помощью оборудования используйте параметр `-hw`.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog -hw  
```  
  
### Проверка файла журнала графики относительно WARP  
 В режиме проверки файл журнала графики воспроизводится как на оборудовании, так и в WARP, после чего результаты сравниваются.  Это может помочь определить ошибки отрисовки, вызванные драйвером.  Чтобы проверить правильность работы графического оборудования в сравнении с WARP, используйте параметр –v.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog  
```  
  
 Чтобы уменьшить количество сравнений, вы можете указать подмножество команд для сравнения; остальные команды будут игнорироваться.  Чтобы указать команды, результаты которых нужно сравнить, используйте параметр –examine.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog –examine present,draw,copy,clear  
```  
  
### Преобразование файла журнала графики в файлы PNG  
 Для просмотра и анализа кадров из файла журнала графики программа DXCap.exe может сохранять захваченные кадры как файлы изображений PNG.  Для получения захваченных кадров в виде файлов PNG используйте параметр `-screenshot` в режиме воспроизведения.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot  
```  
  
 Чтобы указать кадры, которые необходимо получить, используйте параметр `–frame` с параметром `–screenshot`.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot –frame 5, 7-9  
```  
  
### Преобразование файла журнала графики в XML  
 Для обработки и анализа журналов графики с помощью привычных средств, таких как FindStr или XSLT, программа DXCap.exe преобразовать файл журнала графики в формат XML.  Чтобы преобразовать журнал в формат XML вместо его воспроизведения, используйте параметр `-toXML` в режиме воспроизведения.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog –toXML  
```  
  
 По умолчанию выходные данные XML записываются в файл с тем же именем, что и у файла журнала, но с расширением XML.  В приведенном выше примере файл XML получит имя **regression\_test\_12.xml**.  Чтобы присвоить файлу XML другое имя, укажите его после параметра `-toXML`.  
  
```ms-dos  
DXCap.exe –p regression_test_12.vsglog –toXML temp.xml  
```  
  
 Получившийся файл будет содержать код XML наподобие следующего:  
  
```xml  
<Moment value="67"/>  
<Method name="CreateDXGIFactory1" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="riid" type="IID" value="770AAE78-F26F-4DBA-A829-253C83D1B387" />  
    <Parameter name="ppFactory" type="void" handle="1" isOutput="true" />  
</Method>  
  
<Moment value="167"/>  
<Method name="D3D11CreateDevice" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="pAdapter" type="IDXGIAdapter" handle="34" />  
    <Parameter name="DriverType" type="D3D_DRIVER_TYPE" value="D3D_DRIVER_TYPE_UNKNOWN" />  
    <Parameter name="Software" type="HMODULE" value="pointer" />  
    <Parameter name="Flags" type="UINT" value="0" />  
    <Parameter name="pFeatureLevels" type="D3D_FEATURE_LEVEL" arrSize="1" >  
        <Element value="D3D_FEATURE_LEVEL_11_0" />  
    </Parameter>  
    <Parameter name="FeatureLevels" type="UINT" value="1" />  
    <Parameter name="SDKVersion" type="UINT" value="7" />  
    <Parameter name="ppDevice" type="ID3D11Device" handle="35" isOutput="true" />  
    <Parameter name="pFeatureLevel" type="D3D_FEATURE_LEVEL" value="D3D_FEATURE_LEVEL_11_0" isOutput="true" />  
    <Parameter name="ppImmediateContext" type="ID3D11DeviceContext" value="nullptr" isOutput="true" />  
</Method>  
```  
  
## Требования