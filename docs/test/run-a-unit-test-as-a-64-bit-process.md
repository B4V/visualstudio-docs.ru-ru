---
title: "Выполнение модульного теста как 64-разрядного процесса | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: 25
ms.author: douge
manager: douge
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
ms.sourcegitcommit: 5ab78b6b8eaa8156ed2c8a807b1d8a80e75afa84
ms.openlocfilehash: c5a24ac7491631c87acb66b4ed19a2fc082adab3
ms.lasthandoff: 04/04/2017

---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>Выполнение модульного теста как 64-разрядного процесса
На 64-разрядном компьютере можно выполнять модульные тесты и получать данные о покрытии кода в рамках 64-разрядного процесса.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>Выполнение модульного теста как 64-разрядного процесса  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>Выполнение модульного теста как 64-разрядного процесса  
  
1.  Если код или тесты были скомпилированы как 32-разрядные (x86), но вы хотите выполнять их в 64-разрядном процессе, перекомпилируйте их в конфигурации **Любой ЦП** или при необходимости **64 разряда**.  
  
    > [!TIP]
    >  Для максимальной гибкости тестовые проекты следует компилировать в конфигурации **Любой ЦП**. Тогда выполнение возможно как на 32-разрядных, так и на 64-разрядных агентах. Компиляция тестовых проектов в конфигурации **64 разряда** не дает никаких преимуществ.  
  
2.  В меню Visual Studio выберите **Тест**, а затем **Параметры** и **Архитектура процессора**. Выберите **x64**, чтобы выполнять тесты в 64-разрядном процессе.  
  
     \- или -  
  
     Укажите `<TargetPlatform>x64</TargetPlatform>` в RUNSETTINGS-файле. Преимущество этого метода состоит в том, что можно задавать группы настроек в разных файлах и быстро переключаться между различными настройками. Кроме того, вы можете копировать настройки между решениями. Дополнительные сведения см. в разделе [Настройка модульных тестов с помощью файла .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
## <a name="see-also"></a>См. также  
 [Выполнение модульных тестов с помощью обозревателя тестов](../test/run-unit-tests-with-test-explorer.md)   
 [Модульное тестирование кода](../test/unit-test-your-code.md)   
 [Указание параметров тестирования для тестов Visual Studio](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests)
