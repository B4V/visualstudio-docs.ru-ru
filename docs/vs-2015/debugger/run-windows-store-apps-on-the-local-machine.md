---
title: Приложения Windows Store выполнения на локальном компьютере | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e42a21a8-6423-4caf-b4dc-72b263e76019
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b460d1eecfe96cddce27926ee8e31aae258d8dcf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49188389"
---
# <a name="run-windows-store-apps-on-the-local-machine"></a>Запуск приложений для Магазина Windows на локальном компьютере
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Применяется только к Windows] (.. /Image/windows_only_content.PNG «windows_only_content»)  
  
 Чтобы провести отладку, тестирование или анализ производительности для приложения Магазина Windows, вы можете запустить это приложение на том же компьютере, где размещается Visual Studio. Если экран устройства поддерживает сенсорное управление, вам становятся доступны все функции приложения, в противном случае вы сможете использовать только жесты, выполняемые с помощью мыши и клавиатуры.  
  
##  <a name="BKMK_In_this_topic"></a> Содержание раздела  
 В разделе содержится следующая информация:  
  
 [Как запустить на локальном компьютере](#BKMK_How_to_run_on_a_local_machine)  
  
 [Как переключаться между приложения Windows Store и Visual Studio на одном мониторе](#BKMK_How_to_switch_between_a_Windows_Store_app_and_Visual_Studio_on_a_single_monitor)  
  
##  <a name="BKMK_How_to_run_on_a_local_machine"></a> Как запустить на локальном компьютере  
 Чтобы запустить приложение на локальном компьютере, выберите **локального компьютера** из раскрывающегося списка рядом с кнопкой "Начать отладку" в отладчике **стандартный** панели инструментов.  
  
 ![Запуск на локальном компьютере](../debugger/media/vsrun-f5-local.png "VSRUN_F5_Local")  
  
 Если вы не видите **стандартный** панели инструментов нажмите кнопку **представление** последовательно выберите пункты **панелей инструментов**и нажмите кнопку **стандартный**.  
  
 Выбор, производимый в раскрывающемся списке, сохраняется в файле свойств проекта и используется для запуска по умолчанию.  
  
 Целевой объект запуска также можно задать напрямую в файле свойств проекта. Щелкните правой кнопкой мыши имя проекта в **обозревателе решений** и выберите **свойства**. Выполните одно из следующих действий.  
  
-   В проектах C# и Visual Basic щелкните **Отладка** , а затем выберите **локального компьютера** из **целевое устройство** стрелку раскрывающегося списка.  
  
     ![C&#35; и страницу свойств проекта Visual Basic](../debugger/media/vsrun-cs-vb-projprop-local.png "VSRUN_CS_VB_ProjProp_Local")  
  
-   В проектах C++ и JavaScript разверните **свойства конфигурации** узла, нажмите кнопку **Отладка**, а затем выберите **локальный отладчик** из **отладчика Чтобы запустить** списка.  
  
     ![C&#43; &#43; и страницы свойств проекта JavaScript](../debugger/media/vsrun-cpp-js-projprop-local.png "VSRUN_CPP_JS_ProjProp_Local")  
  
##  <a name="BKMK_How_to_switch_between_a_Windows_Store_app_and_Visual_Studio_on_a_single_monitor"></a> Как переключаться между приложения Windows Store и Visual Studio на одном мониторе  
 **Для переключения из работающего экземпляра приложения Windows Store в Visual Studio**  
  
 Если вы запускаете приложение Магазина Windows на локальном компьютере и используете один монитор, вам может потребоваться вернуться в Visual Studio, оставив приложение выполняющимся. Например, приложение может находиться в состоянии, которого нельзя добиться с помощью точки останова, например, ожидать события или выполняться в длительном или бесконечном цикле. Чтобы вернуться в Visual Studio, нажмите ALT+TAB.



