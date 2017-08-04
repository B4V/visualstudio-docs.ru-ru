---
title: "Идентификаторы рабочих нагрузок и компонентов для Visual Studio Enterprise 2017 | Документация Майкрософт"
description: "Идентификаторы рабочих нагрузок и компонентов позволяют устанавливать Visual Studio с помощью командной строки. Также их можно указать в качестве зависимости в манифесте VSIX."
keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.date: 05/10/2017
ms.topic: article
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.prod: visual-studio-dev15
ms.service: 
ms.technology:
- vs-ide-install
- vs-ide-sdk
ms.assetid: be73e3af-d87b-4d14-bd08-2e4bda074fb3
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 25704ab33e59ccea06d2234e3761b3a05106fcdd
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---

# <a name="visual-studio-enterprise-2017-component-directory"></a>Каталог компонентов для Visual Studio Enterprise 2017

В таблицах на этой странице перечислены идентификаторы, которые можно использовать для установки Visual Studio с помощью командной строки или в качестве зависимости в манифесте VSIX. Обратите внимание, что по мере выхода обновлений для Visual Studio здесь будут появляться новые компоненты.

Также обратите внимание на следующие моменты:

* Каждая рабочая нагрузка имеет свой раздел, за которым приводится идентификатор рабочей нагрузки и таблица компонентов, доступных для этой рабочей нагрузки.
* По умолчанию при установке рабочей нагрузки устанавливаются только **обязательные** компоненты. * По желанию вы можете также установить **рекомендуемые** и **дополнительные** компоненты.
* Мы также добавили отдельный раздел для дополнительных компонентов, которые не связаны с конкретными рабочими нагрузками.

Когда вы включаете зависимости в манифест VSIX, достаточно указать только идентификаторы компонентов. Таблицы на этой странице позволяют определить минимальный набор зависимостей компонентов. В некоторых сценариях нужно указать лишь один компонент из рабочей нагрузки. В других случаях потребуется несколько компонентов из одной рабочей нагрузки или несколько компонентов из нескольких рабочих нагрузок. Дополнительные сведения см. в статье [How to: Migrate Extensibility Projects to Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) (Руководство по переносу проектов расширения среды на Visual Studio 2017).


Дополнительные сведения об использовании идентификаторов см. в статье [Использование параметров командной строки для установки версии-кандидата Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md). Список идентификаторов рабочих нагрузок и компонентов для других продуктов вы найдете в статье [Идентификаторы рабочих нагрузок и компонентов Visual Studio 2017](workload-and-component-ids.md).

## <a name="visual-studio-core-editor-included-with-visual-studio-enterprise-2017"></a>Основной редактор Visual Studio (включен в Visual Studio Enterprise 2017)

**Идентификатор.** Microsoft.VisualStudio.Workload.CoreEditor

**Описание.** Основные возможности оболочки Visual Studio, включая редактирование кода с учетом синтаксиса, управление исходным кодом и рабочими элементами.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Обязательное


## <a name="azure-development"></a>Разработка для Azure

**Идентификатор.** Microsoft.VisualStudio.Workload.Azure

**Описание.** Пакет SDK Azure, средства и проекты для разработки облачных приложений и создания ресурсов.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.Component.NetFX.Core.Runtime | Среда выполнения .NET Core | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Core.Component.SDK | Средства разработки .NET Core 1.0.1 | 15.0.26208.0 | Обязательное
Microsoft.NetCore.ComponentGroup.Web | Средства разработки .NET Core 1.0–1.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Azure.ClientLibs | Библиотеки Azure для .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Обязательное
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.ComponentGroup.Azure.Prerequisites | Необходимые компоненты для разработки на базе Azure | 15.0.26323.1 | Обязательное
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Рекомендованное
Microsoft.Component.Azure.DataLake.Tools | Средства Azure Data Lake | 15.0.26208.0 | Рекомендованное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Средства разработки для Azure | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Эмулятор вычислений Azure | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.MobileAppsSdk | Пакет SDK для мобильных приложений Azure | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.ResourceManager.Tools | Основные инструменты Azure Resource Manager | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.ServiceFabric.Tools | Средства Service Fabric | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Эмулятор хранения Azure | 15.0.26424.2 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Waverton | Основные инструменты облачных служб Azure | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Рекомендованное
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Рекомендованное
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Рекомендованное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.ComponentGroup.Azure.CloudServices | Инструменты облачных служб Azure | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.ComponentGroup.Azure.ResourceManager.Tools | Средства Azure Resource Manager | 15.0.26323.1 | Рекомендованное
Microsoft.Net.Component.4.6.2.SDK | Пакет SDK для .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | Пакет SDK для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 Targeting Pack | 15.0.26419.1 | Необязательный
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Средства разработки .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Средства разработки для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.Azure.Storage.AzCopy | AzCopy службы хранилища Azure | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.PowerShell.Tools | Инструменты PowerShell | 3.0.427 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Optional


## <a name="data-storage-and-processing"></a>Хранение и обработка данных

**Идентификатор.** Microsoft.VisualStudio.Workload.Data

**Описание.** Подключение, разработка и тестирование решений по обработке данных с помощью SQL Server, Azure Data Lake, Hadoop или машинного обучения Azure.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.Redgate.ReadyRoll | Redgate ReadyRoll | 1.13.22.3147 | Рекомендованное
Component.Redgate.SQLPrompt.VsPackage | Redgate SQL Prompt | 7.4.1.767 | Рекомендованное
Component.Redgate.SQLSearch.VSExtension | Поиск Redgate SQL | 2.3.10.1131 | Рекомендованное
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Рекомендованное
Microsoft.Component.Azure.DataLake.Tools | Средства Azure Data Lake | 15.0.26208.0 | Рекомендованное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Рекомендованное
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Рекомендованное
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Средства разработки для Azure | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.ClientLibs | Библиотеки Azure для .NET | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Эмулятор вычислений Azure | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Эмулятор хранения Azure | 15.0.26424.2 | Рекомендованное
Microsoft.VisualStudio.Component.Azure.Waverton | Основные инструменты облачных служб Azure | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Рекомендованное
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Рекомендованное
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Рекомендованное
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Рекомендованное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.FSharp | Поддержка языка F# | 15.0.26208.0 | Необязательный


## <a name="data-science-and-analytical-applications"></a>Приложения для обработки и анализа данных и аналитические приложения

**ID:** Microsoft.VisualStudio.Workload.DataScience

**Описание.** Языки и инструменты для создания приложений для обработки и анализа данных, включая Python, R и F#.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.Anaconda3.x64 | 64-разрядная версия Anaconda3 (4.3.0.1) | 4.3.0.2 | Рекомендованное
Microsoft.Component.CookiecutterTools | Поддержка шаблонов Cookiecutter | 15.0.26419.1 | Рекомендованное
Microsoft.Component.PythonTools | Поддержка языка Python | 15.0.26419.1 | Рекомендованное
Microsoft.Component.PythonTools.Web | Поддержка веб-приложений Python | 15.0.26419.1 | Рекомендованное
Microsoft.Component.VC.Runtime.UCRTSDK | Пакет SDK для Windows Universal CRT | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Рекомендованное
Microsoft.VisualStudio.Component.FSharp | Поддержка языка F# | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.R.Open | Microsoft R Client (3.3.2) | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.RHost | Поддержка средств разработки R в среде выполнения | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.RTools | Поддержка языка R | 15.0.26419.1 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Windows81SDK | Пакет SDK для Windows 8.1 | 15.0.26208.0 | Рекомендованное
Component.Anaconda2.x64 | 64-разрядная версия Anaconda2 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.Anaconda2.x86 | 32-разрядная версия Anaconda2 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.Anaconda3.x86 | 32-разрядная версия Anaconda3 (4.3.0.1) | 4.3.0.2 | Необязательный
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Встроенные средства разработки Python | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | Отладчик графики и профилировщик GPU для DirectX | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | Пакет SDK графических инструментов для Windows 8.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | Набор инструментов VC++ 2015.3 версии 140 (x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.VC.DiagnosticTools | Средства профилирования C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.Windows10SDK | Универсальная среда выполнения C для Windows | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Пакет SDK для Windows 10 (10.0.10586.0) | 15.0.26208.0 | Optional


## <a name="net-desktop-development"></a>Разработка классических приложений .NET

**Идентификатор.** Microsoft.VisualStudio.Workload.ManagedDesktop

**Описание.** Разработка приложений WPF, Windows Forms и консольных приложений с использованием .NET Framework.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Debugger.JustInTime | JIT-отладчик | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Обязательно
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | Средства разработки классических приложений .NET | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Обязательное
Microsoft.ComponentGroup.Blend | Blend для Visual Studio | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.EntityFramework | Инструменты для Entity Framework 6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26208.0 | Рекомендованное
Component.Dotfuscator | PreEmptive Protection — Dotfuscator | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | Пакет SDK для .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | Пакет SDK для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 Targeting Pack | 15.0.26419.1 | Необязательный
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Средства разработки .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Средства разработки для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.Net.Core.Component.SDK | Средства разработки .NET Core 1.0.1 | 15.0.26208.0 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools | Средства разработки .NET Core 1.0–1.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Динамическая проверка зависимостей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.FSharp | Поддержка языка F# | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Инструменты архитектуры и анализа | 15.0.26208.0 | Optional


## <a name="game-development-with-unity"></a>Разработка игр с помощью Unity

**Идентификатор.** Microsoft.VisualStudio.Workload.ManagedGame

**Описание.** Создание двухмерных и трехмерных игр с помощью мощной кроссплатформенной среды разработки Unity.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Unity | Набор средств Visual Studio для Unity | 15.0.26323.1 | Обязательное
Component.UnityEngine | Редактор Unity 5.6 | 15.0.26430.4 | Рекомендованное


## <a name="linux-development-with-c"></a>Разработка приложений для Linux на C++

**Идентификатор.** Microsoft.VisualStudio.Workload.NativeCrossPlat

**Описание.** Создание и отладка приложений, запускаемых в среде Linux.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.MDD.Linux | Visual C++ для разработки в среде Linux | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Windows10SDK | Универсальная среда выполнения C для Windows | 15.0.26208.0 | Обязательное


## <a name="desktop-development-with-c"></a>Разработка классических приложений на C++

**Идентификатор.** Microsoft.VisualStudio.Workload.NativeDesktop

**Описание.** Создание классических приложений для Windows с помощью набора инструментов Visual C++, библиотеки ATL и дополнительных средств, таких как MFC и C++/CLI.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.ClassDesigner | Конструктор классов | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Debugger.JustInTime | JIT-отладчик | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Native | Инструменты разработки архитектуры для C++ | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Основные возможности Visual C++ для классических приложений | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Graphics.Tools | Отладчик графики и профилировщик GPU для DirectX | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Graphics.Win81 | Пакет SDK графических инструментов для Windows 8.1 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.CMake.Project | Инструменты Visual C++ для CMake | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.DiagnosticTools | Средства профилирования C++ | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Пакет SDK для Windows 10 (10.0.15063.0) для Desktop C++ x86 и x64 | 15.0.26403.0 | Рекомендованное
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Пакет SDK для Windows Universal CRT | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | Набор инструментов VC++ 2015.3 версии 140 (x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Поддержка библиотеки ATL для Visual C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | Поддержка библиотек MFC и ATL (x86 и x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (экспериментальная версия) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | Поддержка C++/CLI | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | Модули стандартных библиотек | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Пакет SDK для Windows 10 (10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Пакет SDK для Windows 10 (10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Пакет SDK для Windows 10 (10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Пакет SDK для Windows 8.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.WinXP | Поддержка Windows XP для C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Пакеты SDK для Windows 8.1 и UCRT | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | Поддержка Windows XP для C++ | 15.0.26208.0 | Optional


## <a name="game-development-with-c"></a>Разработка игр на C++

**Идентификатор.** Microsoft.VisualStudio.Workload.NativeGame

**Описание.** Используйте все возможности C++ для создания профессиональных игр на базе DirectX, Unreal или Cocos2D.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Windows10SDK | Универсальная среда выполнения C для Windows | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Graphics.Tools | Отладчик графики и профилировщик GPU для DirectX | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Graphics.Win81 | Пакет SDK графических инструментов для Windows 8.1 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.DiagnosticTools | Средства профилирования C++ | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Пакет SDK для Windows 10 (10.0.15063.0) для Desktop C++ x86 и x64 | 15.0.26403.0 | Рекомендованное
Component.Cocos | Cocos | 15.0.26323.1 | Optional
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Component.Unreal | Установщик Unreal Engine | 15.0.26323.1 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Пакет SDK для Windows Universal CRT | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Пакет SDK для Windows 10 (10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Пакет SDK для Windows 10 (10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Пакет SDK для Windows 10 (10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Пакет SDK для Windows 8.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Пакеты SDK для Windows 8.1 и UCRT | 15.0.26208.0 | Optional


## <a name="mobile-development-with-c"></a>Разработка мобильных приложений на C++

**Идентификатор.** Microsoft.VisualStudio.Workload.NativeMobile

**Описание.** Создание кроссплатформенных приложений на С++ для iOS, Android или Windows.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Обязательное
Component.Android.NDK.R13B | Пакет NDK для Android (R13B) | 13.1.6 | Рекомендованное
Component.Android.SDK19 | Установка пакета SDK для Android (уровни API 19 и 21) | 15.0.26208.0 | Рекомендованное
Component.Android.SDK22 | Установка пакета SDK для Android (уровень API 22) | 15.0.26208.0 | Рекомендованное
Component.Ant | Apache Ant (1.9.3) | 1.9.3.7 | Рекомендованное
Component.MDD.Android | Средства разработки на C++ для Android | 15.0.26208.0 | Рекомендованное
Component.Android.NDK.R11C | Пакет NDK для Android (R11C) | 11.3.13 | Optional
Component.Android.NDK.R11C_3264 | Пакет NDK для Android (R11C) (32-разрядная версия) | 11.3.14 | Optional
Component.Android.NDK.R12B | Пакет NDK для Android (R12B) | 12.1.9 | Optional
Component.Android.NDK.R12B_3264 | Пакет NDK для Android (R12B) (32-разрядная версия) | 12.1.9 | Optional
Component.Android.NDK.R13B_3264 | Пакет NDK для Android (R13B) (32-разрядная версия) | 13.1.6 | Optional
Component.Android.SDK23 | Установка пакета SDK для Android (уровень API 23) | 15.0.26208.0 | Optional
Component.Google.Android.Emulator.API23.V2 | Эмулятор Google Android (уровень API 23) | 15.0.26208.0 | Optional
Component.HAXM | Intel Hardware Accelerated Execution Manager (HAXM) | 15.0.26208.0 | Optional
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Component.JavaJDK | Пакет разработки для Java SE (8.0.1120.15) | 15.0.26403.0 | Optional
Component.MDD.IOS | Средства разработки C++ для iOS | 15.0.26208.0 | Optional


## <a name="net-core-cross-platform-development"></a>Кроссплатформенная разработка .NET Core

**Идентификатор.** Microsoft.VisualStudio.Workload.NetCoreTools

**Описание.** Создание кроссплатформенных приложений с помощью .NET Core, ASP.NET Core, HTML, JavaScript и CSS.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Core.Component.SDK | Средства разработки .NET Core 1.0.1 | 15.0.26208.0 | Обязательное
Microsoft.NetCore.ComponentGroup.Web | Средства разработки .NET Core 1.0–1.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Обязательное
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Обязательно
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.DockerTools | Средства разработки контейнеров | 15.0.26323.1 | Рекомендованное


## <a name="mobile-development-with-net"></a>Разработка мобильных приложений на платформе .NET

**Идентификатор.** Microsoft.VisualStudio.Workload.NetCrossPlat

**Описание.** Создание кроссплатформенных приложений для iOS, Android или Windows с помощью Xamarin.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Component.Android.NDK.R13B | Пакет NDK для Android (R13B) | 13.1.6 | Рекомендованное
Component.Android.SDK23 | Установка пакета SDK для Android (уровень API 23) | 15.0.26208.0 | Рекомендованное
Component.Google.Android.Emulator.API23.V2 | Эмулятор Google Android (уровень API 23) | 15.0.26208.0 | Рекомендованное
Component.HAXM | Intel Hardware Accelerated Execution Manager (HAXM) | 15.0.26208.0 | Рекомендованное
Component.JavaJDK | Пакет разработки для Java SE (8.0.1120.15) | 15.0.26403.0 | Рекомендованное
Component.Xamarin | Xamarin | 15.0.26424.2 | Рекомендованное
Component.Xamarin.Inspector | Xamarin Workbooks | 15.0.26228.0 | Рекомендованное
Component.Xamarin.Profiler | Xamarin Profiler | 15.0.26228.0 | Рекомендованное
Component.Xamarin.RemotedSimulator | Симулятор удаленной работы для Xamarin | 15.0.26228.0 | Рекомендованное
Microsoft.VisualStudio.Component.FSharp | Поддержка языка F# | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Рекомендованное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Динамическая проверка зависимостей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | Редакторы изображений и трехмерных моделей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Эмулятор мобильных устройств с ОС Windows 10 (Creators Update) | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Пакет SDK для Windows 10 (10.0.15063.0) для UWP: C#, VB, JS | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Инструменты архитектуры и анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Средства универсальной платформы Windows для Xamarin | 15.0.26403.0 | Optional


## <a name="aspnet-and-web-development"></a>ASP.NET и веб-разработка

**Идентификатор.** Microsoft.VisualStudio.Workload.NetWeb

**Описание.** Создание веб-приложений с помощью ASP.NET, ASP.NET Core, HTML, JavaScript и CSS.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Core.Component.SDK | Средства разработки .NET Core 1.0.1 | 15.0.26208.0 | Обязательное
Microsoft.NetCore.ComponentGroup.Web | Средства разработки .NET Core 1.0–1.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Обязательное
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Обязательно
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Рекомендованное
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DockerTools | Средства разработки контейнеров | 15.0.26323.1 | Рекомендованное
Microsoft.VisualStudio.Component.EntityFramework | Инструменты для Entity Framework 6 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Рекомендованное
Microsoft.Net.Component.4.6.2.SDK | Пакет SDK для .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | Пакет SDK для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 Targeting Pack | 15.0.26419.1 | Необязательный
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | Средства разработки .NET Framework 4.6.2 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | Средства разработки для .NET Framework 4.7 | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.ClassDesigner | Конструктор классов | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Динамическая проверка зависимостей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.FSharp | Поддержка языка F# | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Инструменты архитектуры и анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Web.Mvc4.ComponentGroup | ASP.NET MVC 4 | 15.0.26208.0 | Optional


## <a name="nodejs-development"></a>Разработка Node.js

**Идентификатор.** Microsoft.VisualStudio.Workload.Node

**Описание.** Разработка масштабируемых сетевых приложений с помощью Node.js, асинхронной управляемой событиями среды выполнения JavaScript.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.Node.Tools | Поддержка Node.js | 15.0.26323.1 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Рекомендованное
Microsoft.VisualStudio.Component.Git | Git для Windows | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Optional


## <a name="officesharepoint-development"></a>Разработка для Office и SharePoint

**Идентификатор.** Microsoft.VisualStudio.Workload.Office

**Описание.** Создание надстроек для Office и SharePoint, решений SharePoint и надстроек для VSTO на языках C#, VB и JavaScript.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Обязательное
Microsoft.VisualStudio.Component.Debugger.JustInTime | JIT-отладчик | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Обязательно
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | Средства разработки классических приложений .NET | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Sharepoint.Tools | Инструменты разработчика Office для Visual Studio | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Workflow | Windows Workflow Foundation | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.TeamOffice | Набор средств Visual Studio для Office (VSTO) | 15.0.26228.0 | Рекомендованное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Необязательный


## <a name="python-development"></a>Разработка на Python

**ID:** Microsoft.VisualStudio.Workload.Python

**Описание:** редактирование, отладка, интерактивная разработка и управление версиями для Python.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.CPython3.x64 | 64-разрядная версия Python 3 (3.6.0) | 3.6.0 | Рекомендованное
Microsoft.Component.CookiecutterTools | Поддержка шаблонов Cookiecutter | 15.0.26419.1 | Рекомендованное
Microsoft.Component.PythonTools | Поддержка языка Python | 15.0.26419.1 | Рекомендованное
Microsoft.Component.PythonTools.Web | Поддержка веб-приложений Python | 15.0.26419.1 | Рекомендованное
Microsoft.Component.VC.Runtime.UCRTSDK | Пакет SDK для Windows Universal CRT | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Common.Azure.Tools | Средства подключения и публикации | 1.9.170119.3 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.WebDeploy | Web Deploy | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.Windows81SDK | Пакет SDK для Windows 8.1 | 15.0.26208.0 | Рекомендованное
Component.Anaconda2.x64 | 64-разрядная версия Anaconda2 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.Anaconda2.x86 | 32-разрядная версия Anaconda2 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.Anaconda3.x64 | 64-разрядная версия Anaconda3 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.Anaconda3.x86 | 32-разрядная версия Anaconda3 (4.3.0.1) | 4.3.0.2 | Необязательный
Component.CPython2.x64 | 64-разрядная версия Python 2 (2.7.13) | 2.7.13 | Необязательный
Component.CPython2.x86 | 32-разрядная версия Python 2 (2.7.13) | 2.7.13 | Необязательный
Component.CPython3.x86 | 32-разрядная версия Python 3 (3.6.0) | 3.6.0.1 | Необязательный
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Необязательный
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Optional
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | Необязательный
Microsoft.Component.PythonTools.UWP | Поддержка Интернета вещей для Python | 15.0.26419.1 | Необязательный
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Встроенные средства разработки Python | 15.0.26419.1 | Необязательный
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.TargetingPacks.Common | Средства разработки для .NET Framework 4–4.6 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Необязательный
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Средства разработки для Azure | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.Azure.ClientLibs | Библиотеки Azure для .NET | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Эмулятор вычислений Azure | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Эмулятор хранения Azure | 15.0.26424.2 | Необязательный
Microsoft.VisualStudio.Component.Azure.Waverton | Основные инструменты облачных служб Azure | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.ClassDesigner | Конструктор классов | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.CoreEditor | Основной редактор Visual Studio | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | Редакторы изображений и трехмерных моделей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | Отладчик графики и профилировщик GPU для DirectX | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | Пакет SDK графических инструментов для Windows 8.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Необязательный
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Основные средства рабочей нагрузки управляемого рабочего стола | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.SQL.ADAL | Среда выполнения SQL ADAL | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.SQL.CMDUtils | Служебные программы командной строки SQL Server | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.SQL.DataSources | Источники данных для поддержки SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Необязательный
Microsoft.VisualStudio.Component.VC.140 | Набор инструментов VC++ 2015.3 версии 140 (x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.VC.DiagnosticTools | Средства профилирования C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Необязательный
Microsoft.VisualStudio.Component.Web | ASP.NET и средства веб-разработки | 15.0.26323.1 | Необязательный
Microsoft.VisualStudio.Component.Windows10SDK | Универсальная среда выполнения C для Windows | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Пакет SDK для Windows 10 (10.0.10586.0) | 15.0.26208.0 | Optional


## <a name="universal-windows-platform-development"></a>Разработка с помощью универсальной платформы Windows

**Идентификатор.** Microsoft.VisualStudio.Workload.Universal

**Описание.** Создание приложений для универсальной платформы Windows с помощью C#, VB, JavaScript или C++.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | Обязательное
Microsoft.ComponentGroup.Blend | Blend для Visual Studio | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Graphics | Редакторы изображений и трехмерных моделей | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Microsoft.VisualStudio.Component.UWP.Support | Средства универсальной платформы Windows | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Пакет SDK для Windows 10 (10.0.15063.0) для UWP: C#, VB, JS | 15.0.26419.1 | Обязательно
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Средства универсальной платформы Windows для Cordova | 15.0.26403.0 | Обязательное
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Средства универсальной платформы Windows для Xamarin | 15.0.26403.0 | Обязательное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Рекомендованное
Microsoft.Component.VC.Runtime.OSSupport | Среда выполнения Visual C++ для UWP | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Динамическая проверка зависимостей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | Отладчик графики и профилировщик GPU для DirectX | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | Пакет SDK графических инструментов для Windows 8.1 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Эмулятор мобильных устройств с ОС Windows 10 (Creators Update) | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | Компиляторы и библиотеки Visual C++ для ARM | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Пакет SDK для Windows 10 (10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Пакет SDK для Windows 10 (10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Пакет SDK для Windows 10 (10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Пакет SDK для Windows 10 (10.0.15063.0) для UWP: C++ | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Инструменты архитектуры и анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.VC | Средства универсальной платформы Windows для C++ | 15.0.26403.0 | Optional


## <a name="visual-studio-extension-development"></a>Разработка расширений Visual Studio

**Идентификатор.** Microsoft.VisualStudio.Workload.VisualStudioExtension

**Описание.** Создание надстроек и расширений для Visual Studio. Содержит новые команды, анализаторы кода и окна инструментов.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.SDK | Пакет SDK для .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 Targeting Pack | 15.0.26208.0 | Обязательное
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | Средства разработки .NET Framework 4.6.1 | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.NuGet | Диспетчер пакетов NuGet | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.PortableLibrary | Пакет нацеливания переносимой библиотеки .NET | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.ComponentGroup.VisualStudioExtension.Prerequisites | Необходимые компоненты для разработки расширений Visual Studio | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.CodeClone | Клон кода | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.CodeMap | Представление кода | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Динамическая проверка зависимостей | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.GraphDocument | Редактор DGML | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | LocalDB для экспресс-выпуска SQL Server 2016 | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.Component.SQL.NCLI | Собственный клиент SQL Server | 15.0.26208.0 | Рекомендованное
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Инструменты архитектуры и анализа | 15.0.26208.0 | Рекомендованное
Component.Dotfuscator | PreEmptive Protection — Dotfuscator | 15.0.26208.0 | Optional
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Optional
Microsoft.Component.VC.Runtime.OSSupport | Среда выполнения Visual C++ для UWP | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 Targeting Pack | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.ClassDesigner | Конструктор классов | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DslTools | Пакет SDK для моделирования | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | Компиляторы Roslyn для C# и Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# и Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Инструменты статического анализа | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.TextTemplating | Преобразование текстовых шаблонов | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Поддержка библиотеки ATL для Visual C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | Поддержка библиотек MFC и ATL (x86 и x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Основные компоненты Visual Studio C++ | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | Набор инструментов VC++ 2017 версии 141 (x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VSSDK | SDK для Visual Studio | 15.0.26208.0 | Optional


## <a name="mobile-development-with-javascript"></a>Разработка мобильных приложений на языке JavaScript

**Идентификатор.** Microsoft.VisualStudio.Workload.WebCrossPlat

**Описание.** Разработка приложений Android, iOS и UWP с помощью средств для Apache Cordova.

### <a name="components-included-by-this-workload"></a>Компоненты, используемые этой рабочей нагрузкой

Идентификатор компонента | Имя | Версия | Тип зависимости
--- | --- | --- | ---
Component.CordovaToolset.6.3.1 | Набор инструментов Cordova 6.3.1 | 15.0.26323.1 | Обязательное
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.Cordova | Основные компоненты для разработки мобильных приложений на JavaScript | 15.0.26323.1 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | Диагностика JavaScript | 15.0.26208.0 | Обязательное
Microsoft.VisualStudio.Component.JavaScript.TypeScript | Поддержка языков JavaScript и TypeScript | 15.0.26412.1 | Обязательно
Microsoft.VisualStudio.Component.TypeScript.2.2 | Пакет SDK для TypeScript 2.2 | 15.0.26430.1 | Обязательно
Component.Android.SDK23 | Установка пакета SDK для Android (уровень API 23) | 15.0.26208.0 | Optional
Component.Google.Android.Emulator.API23.V2 | Эмулятор Google Android (уровень API 23) | 15.0.26208.0 | Optional
Component.HAXM | Intel Hardware Accelerated Execution Manager (HAXM) | 15.0.26208.0 | Optional
Component.JavaJDK | Пакет разработки для Java SE (8.0.1120.15) | 15.0.26403.0 | Optional
Microsoft.Component.ClickOnce | Компонент для публикации ClickOnce | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET Native | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | Средства анализа для разработчиков | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | Средства профилирования | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Git | Git для Windows | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | Редакторы изображений и трехмерных моделей | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Эмулятор мобильных устройств с ОС Windows 10 (Creators Update) | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.Component.SQL.CLR | Типы данных среды CLR для SQL Server | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VisualStudioData | Источники данных и ссылки на службы | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Пакет SDK для Windows 10 (10.0.15063.0) для UWP: C#, VB, JS | 15.0.26419.1 | Необязательный
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Средства универсальной платформы Windows для Cordova | 15.0.26403.0 | Optional
## <a name="unaffiliated-components"></a>Самостоятельные компоненты

Здесь перечислены компоненты, которые не используются рабочими нагрузками, но могут быть выбраны в качестве отдельного компонента.

Идентификатор компонента | Имя | Версия
--- | --- | ---
Component.Android.Emulator | Эмулятор Visual Studio для Android | 15.0.26430.1
Component.GitHub.VisualStudio | Расширение GitHub для Visual Studio | 2.2.0.10
Microsoft.Component.Blend.SDK.WPF | Blend для пакета SDK для Visual Studio для .NET | 15.0.26208.0
Microsoft.Component.HelpViewer | Help Viewer | 15.0.26208.0
Microsoft.Net.Component.3.5.DeveloperTools | Средства разработки для .NET Framework 3.5 | 15.0.26208.0
Microsoft.VisualStudio.Component.LinqToSql | Инструменты LINQ to SQL | 15.0.26208.0
Microsoft.VisualStudio.Component.Phone.Emulator | Эмулятор Windows 10 Mobile (Anniversary Edition) | 15.0.26208.0
Microsoft.VisualStudio.Component.TestTools.CodedUITest | Закодированный тест ИП | 15.0.26208.0
Microsoft.VisualStudio.Component.TestTools.Core | Основные компоненты средств тестирования | 15.0.26208.0
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Feedback Client | 15.0.26208.0
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.0.26228.0
Microsoft.VisualStudio.Component.TestTools.WebLoadTest | Инструменты веб-тестирования производительности и нагрузочного тестирования | 15.0.26208.0
Microsoft.VisualStudio.Component.TypeScript.2.0 | Пакет SDK для TypeScript 2.0 | 15.0.26208.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | Пакет SDK для TypeScript 2.1 | 15.0.26208.0

## <a name="see-also"></a>См. также

* [Идентификаторы рабочих нагрузок и компонентов Visual Studio](workload-and-component-ids.md)
* [Руководство администратора Visual Studio](visual-studio-administrator-guide.md)
* [Использование параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
  * [Примеры параметров командной строки](command-line-parameter-examples.md)
* [Создание автономной установки Visual Studio](create-an-offline-installation-of-visual-studio.md)
