---
title: Параметр DevEnv Build
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds, command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
- command-line builds
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdd510e523aaabc468c1f01626593e51d0ad1558
ms.sourcegitcommit: 9571742f4a808c75b1034aa72fc24b54bc50692e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410966"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

Выполняет сборку решения с использованием заданного файла конфигурации решения.

## <a name="syntax"></a>Синтаксис

```cmd
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]
```

## <a name="arguments"></a>Аргументы

|||
|-|-|
|*SolutionName*|Обязательно. Полный путь и имя для файла решения.|
|*SolnConfigName*|Обязательно. Имя конфигурации решения, которая будет применяться для сборки решения, указанного в *SolutionName*. Если доступно несколько платформ решений, необходимо также указать платформу, например **"Debug\|Win32"**.|
|/project *ProjName*|Необязательный. Путь и имя для файла проекта в решении. Можно ввести относительный путь из папки *SolutionName* к файлу проекта, отображаемое имя проекта или полный путь и имя для файла проекта.|
|/projectconfig *ProjConfigName*|Необязательный. Имя конфигурации сборки проекта, которая применяется при сборке указанного проекта. Если доступно несколько платформ проектов, необходимо также указать платформу, например **"Debug\|Win32"**.|

## <a name="remarks"></a>Примечания

- Параметр **/build** выполняет те же функции, что и команда меню **Собрать решение** в интегрированной среде разработки (IDE).

- Строки с пробелами заключаются в двойные кавычки.

- Сводные данные для сборок, включая ошибки, могут отображаться в окне команд или в любом файле журнала, указанном с помощью параметра **/out**.

- Параметр **/build** выполняет сборку только тех проектов, которые изменились с момента последней сборки. Чтобы выполнить сборку всех проектов в решении, используйте [/rebuild](../../ide/reference/rebuild-devenv-exe.md).

- Если возникает сообщение об ошибке **Недопустимая конфигурация проекта**, убедитесь, что указали платформу решения или проекта, например **"Debug\|Win32"**.

## <a name="example"></a>Пример

Следующая команда создает проект CSharpConsoleApp, используя конфигурацию сборки проекта Debug в конфигурации решения Debug в MySolution.

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>См. также

- [Сборка и очистка проектов и решений](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Параметры командной строки для devenv](../../ide/reference/devenv-command-line-switches.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)