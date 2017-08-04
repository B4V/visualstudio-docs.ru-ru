---
title: "Свойства файлов (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- javascript.project.property.expandedsdknode.fileversion
- javascript.project.property.expandedsdknode.uri
- javascript.project.property.expandedsdknode.filename
- javascript.project.property.reference.description
- javascript.project.property.reference.specificversion
- javascript.project.property.reference.identity
- javascript.project.property.fullpath
- javascript.project.property.packageaction
- javascript.project.property.reference.package
- javascript.project.property.copytooutputdirectory
- javascript.project.property.expandedsdknode.sdkpath
- javascript.project.property.reference.filetype
- javascript.project.property.reference.culture
- javascript.project.property.filename
- javascript.project.property.reference.resolvedpath
- javascript.project.property.reference.version
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d2f4eba36e9069a35cf279ccf1c78f72a51d77a1
ms.openlocfilehash: 6c2b3c577685fcb09cd9e9c7eeee955b75e76e27
ms.contentlocale: ru-ru
ms.lasthandoff: 06/23/2017

---
# <a name="file-properties-javascript"></a>Свойства файлов (JavaScript)
Свойства файлов можно использовать, чтобы указать, какие действия с файлами должны выполняться системой проекта. Например, можно задать свойства файла, чтобы указать, что файл необходимо добавить в пакет как файл ресурсов.  

 Можно выбрать любой файл в обозревателе решений, а затем просмотреть его свойства в окне "Свойства". Файлы JavaScript имеют четыре свойства: **Копировать в выходной каталог**, **Действие пакета**, **Имя файла** и **Путь к файлу**.  

## <a name="file-properties"></a>Свойства файла  
 В этом разделе описываются свойства, общие для файлов JavaScript.  

### <a name="copy-to-output-directory-property"></a>Свойство "Копировать в выходной каталог"  
 Это свойство определяет условия, при которых выбранный исходный файл копируется в выходной каталог. Выберите **Не копировать**, если файл не следует копировать в выходной каталог ни при каких обстоятельствах. Выберите **Всегда копировать**, если файл следует всегда копировать в выходной каталог. Выберите **Копировать, если новее**, если файл требуется копировать только в том случае, если он новее, чем существующий файл с тем же именем в выходном каталоге.  

### <a name="package-action"></a>Действие пакета  
 Свойство **Действие пакета** указывает, какое действие Visual Studio выполняет с файлом при сборке. **Действие пакета** может иметь одно из следующих значений.  

-   **Нет** — файл не включается в манифест пакета. Примером является текстовый файл документации, например файл сведений (Readme).  

-   **Содержимое** — файл включается в манифест пакета. Например этот параметр является значением по умолчанию для HTM-, JS-, CSS-файлов и файлов изображения, аудио или видео.  

-   **Манифест** — файл не включается в манифест пакета. Вместо этого файл используется в качестве входных данных при создании манифеста пакета. Это значение по умолчанию для файла package.appxmanifest.  

-   **Ресурс** — файл не включается в манифест пакета. Вместо этого содержимое файла индексируется в индексе ресурсов пакета, который входит в манифест пакета. Обычно используется для файлов ресурсов.  

 Значение по умолчанию для свойства **Действие пакета** зависит от расширения файла, добавляемого в решение.  

### <a name="file-name-property"></a>Свойство "Имя файла"  
 Отображает имя файла как значение только для чтения. Чтобы переименовать файл, щелкните его правой кнопкой мыши в обозревателе решений и выберите **Переименовать**.  

### <a name="full-path-property"></a>Свойство "Полный путь"  
 Отображает полный путь к файлу как значение только для чтения. Чтобы изменить путь к файлу, можно перетащить файл в обозреватель решений.  

## <a name="reference-file-properties"></a>Свойства файлов ссылок  
 В этом разделе описываются свойства, общие для файлов, на которые имеются ссылки из [!INCLUDE[win8_app_js](../../ide/reference/includes/win8_app_js_md.md)]. При выборе ссылки, такой как WINMD-файл, ссылка на SDK, ссылка проекта на проект или ссылка на сборку, в обозревателе решений другие свойства могут отображаться в окне "Свойства" в соответствии с типом файла.  

### <a name="culture"></a>Язык и региональные параметры  
 Отображает язык, связанный со ссылкой.  

### <a name="file-type"></a>Тип файла  
 Отображает тип файла ссылки.  

### <a name="file-version"></a>Версия файла  
 Отображает версию файла ссылки.  

### <a name="identity"></a>Удостоверение  
 Отображает удостоверение ссылки, используемое в проекте, которое хранится в файле проекта.  

### <a name="package"></a>Пакет  
 Отображает имя манифеста пакета, связанного со ссылкой.  

### <a name="resolved-path"></a>Разрешаемый путь  
 Отображает путь к ссылке, используемой в проекте.  

### <a name="sdk-path"></a>Путь к пакету SDK  
 Отображает путь к файлу пакета SDK, на который указывает ссылка.  

### <a name="uri"></a>URI  
 Отображает URI, который должен быть включен в файлы HTML или JavaScript проекта для включения файла в качестве исходного.  

### <a name="version"></a>Версия  
 Отображает версию, на которую указывает ссылка.  

## <a name="see-also"></a>См. также  
 [Управление свойствами проектов и решений](../../ide/managing-project-and-solution-properties.md)
