---
title: Расширение схем слоев | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- layer diagrams, creating extensions
- layer models
ms.assetid: 83fca301-b008-485a-87eb-218050e71451
caps.latest.revision: 41
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: d3c149558f53effff29d15bfce0d05f0dada0f7b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49847075"
---
# <a name="extend-layer-diagrams"></a>Extend layer diagrams
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вы можете написать код для создания и обновления схем слоев и для проверки структуры кода программы по схемам слоев в Visual Studio. Вы можете добавить команды, которые отображаются в контекстном меню схем, настроить жесты перетаскивания, а также получить доступ к модели слоев из текстовых шаблонов. Вы можете упаковать эти расширения в расширение Visual Studio Integration Extension (VSIX) и предоставить их другим пользователям Visual Studio.  
  
 Более подробную информацию о схемах слоев см. в следующих разделах:  
  
-   [Схемы слоев: справочные материалы](../modeling/layer-diagrams-reference.md)  
  
-   [Схемы слоев: рекомендации](../modeling/layer-diagrams-guidelines.md)  
  
-   [Создание схем слоев на основе кода](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="prereqs"></a> Требования  
 На компьютере, где планируется разрабатывать расширения слоев, должны быть установлены следующие компоненты:  
  
- Visual Studio  
  
- [SDK для Visual Studio](../extensibility/visual-studio-sdk.md)  
  
- [Пакет SDK моделирования для Visual Studio 2015](http://www.microsoft.com/download/details.aspx?id=48148)  
  
  На компьютере, где планируется выполнять расширения слоев, должна быть установлена подходящая версия Visual Studio. Дополнительные сведения см. в разделе [развертывание расширения модели слоев](../modeling/deploy-a-layer-model-extension.md).  
  
  Чтобы узнать, какие версии Visual Studio поддерживают схемы слоев, см. раздел [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Добавление команд и жестов в схемы слоев](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [Добавление пользовательской проверки архитектуры в схемы слоев](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [Добавление пользовательских свойств в схемы слоев](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [Перемещение по моделям слоев в коде программы и их обновление](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [Развертывание расширения модели слоев](../modeling/deploy-a-layer-model-extension.md)  
  
 [Устранение неполадок, связанных с расширениями для схем слоев](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>См. также  
 [Определение и Установка расширения моделирования](../modeling/define-and-install-a-modeling-extension.md)   
 [Схемы слоев: ссылка](../modeling/layer-diagrams-reference.md)   
 [Схемы слоев: рекомендации](../modeling/layer-diagrams-guidelines.md)   
 [Создание схем слоев из кода](../modeling/create-layer-diagrams-from-your-code.md)   
 [Проверка кода по схемам слоев](../modeling/validate-code-with-layer-diagrams.md)   
 [Создание файлов из модели UML](../modeling/generate-files-from-a-uml-model.md)   
 [Открытие модели UML с помощью API Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md)



