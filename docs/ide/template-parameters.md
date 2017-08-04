---
title: "Параметры шаблона | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "шаблоны элементов, параметры"
  - "шаблоны проектов, параметры"
  - "параметры шаблонов [Visual Studio]"
  - "шаблоны Visual Studio, параметры"
ms.assetid: 1b567143-08c6-4d7a-b484-49f0671754fe
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# Параметры шаблона
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

С помощью параметров в шаблонах, можно заменить значения ключевых частей шаблона, например имена классов и пространства имен, когда шаблон будет создан экземпляр.  Эти параметры заменяются при помощи мастера шаблонов, работающего в фоновом режиме, когда пользователь нажимает кнопку **OK** в диалоговых окнах **Новый проект** или **Добавить новый элемент**.  
  
## Объявление и включение параметров шаблона  
 Параметры шаблона объявляются в формате $*parameter*$.  Например:  
  
-   $safeprojectname$  
  
-   $guid1$  
  
-   $guid5$  
  
#### Чтобы включить подстановку параметров в шаблонах  
  
1.  В файле VSTEMPLATE шаблона найдите элемент `ProjectItem`, соответствующий элементу, для которого необходимо заменить параметры.  
  
2.  Задайте атрибут `ReplaceParameters` элемента `ProjectItem` равным `true`.  
  
3.  В файле кода включите соответствующие параметры для элемента проекта.  Например, следующий параметр указывает, что для пространства имен в файле используется безопасное имя проекта:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
## Зарезервированные параметры шаблона  
 Ниже в таблице перечислены зарезервированные параметры шаблона, которые могут быть использованы любым шаблоном.  
  
> [!NOTE]
>  Параметры шаблонов учитывают регистр.  
  
|Параметр|Описание|  
|--------------|--------------|  
|`clrversion`|Текущая версия общеязыковой среды выполнения \(CLR\).|  
|`GUID [1-10]`|Идентификатор GUID, используемый для замены идентификатора GUID проекта в файле проекта.  Можно указать до 10 уникальных идентификаторов GUID \(например, `guid1)`.|  
|`itemname`|Имя задается пользователем в диалоговое окно **Добавление нового элемента**.|  
|`machinename`|Текущее имя компьютера \(например Computer01\).|  
|`projectname`|Имя задается пользователем в диалоговом окне **Новый проект**.|  
|`registeredorganization`|Значение ключа реестра из HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\RegisteredOrganization.|  
|`rootnamespace`|Корневое пространство имен текущего проекта.  Этот параметр применяется только в шаблоны элементов.|  
|`safeitemname`|Имя, указанное пользователем в диалоговом окне **Добавление нового элемента**, с удалением всех небезопасных знаков и пробелов.|  
|`safeprojectname`|Имя, указанное пользователем в диалоговом окне **Добавление нового проекта**, с удалением всех небезопасных знаков и пробелов.|  
|`time`|Текущее время в формате дд\/мм\/гггг 00:00:00.|  
|`SpecificSolutionName`|Имя решения.  При установке «создать каталог решения», `SpecificSolutionName` имеет имя решения.  Когда «создать каталог решения» не установлен, `SpecificSolutionName` пуст.|  
|`userdomain`|Текущий домен пользователя.|  
|`username`|Текущее имя пользователя.|  
|`webnamespace`|Имя текущего веб\-узла.  Этот параметр используется в шаблоне веб\-формы, чтобы гарантировать уникальные имена классов.  Если веб\-узел находится в корневом каталоге веб\-сервера, этот параметр шаблона определяет корневой каталог веб\-сервера.|  
|`year`|Текущий год в формате гггг.|  
  
## Пользовательские параметры шаблона  
 Можно определить собственные параметры шаблона и значения, в дополнение к зарезервированным параметрам шаблона по умолчанию, которые используются во время замещения параметра. Дополнительные сведения см. в разделе [Элемент CustomParameters \(шаблоны Visual Studio\)](../extensibility/customparameters-element-visual-studio-templates.md).  
  
## Пример: замена имен файлов  
 Можно указать переменные имена файлов для элементов проекта с помощью параметра с атрибутом `TargetFileName`.  Например, можно указать, что файл EXE использует имя проекта, указанное в параметре `$projectname$`, в качестве имени файла.  
  
```  
<TemplateContent>  
    <ProjectItem  
        ReplaceParameters="true"  
        TargetFileName="$projectname$.exe">  
            File1.exe  
    </ProjectItem>  
      ...  
</TemplateContent>  
```  
  
## Пример: использовать имя проекта для имени пространства имен  
 Чтобы использовать имя проекта для пространства имен в файле класса Visual C\#, Class1.cs, используйте следующий синтаксис:  
  
```  
#region Using directives  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
#endregion  
  
namespace $safeprojectname$  
{  
    public class Class1  
        {  
            public Class1()  
                {  
  
                }  
         }  
}  
```  
  
 При ссылке на файл Class1.cs в файле VSTEMPLATE для шаблона проекта, включите следующий текст XML:  
  
```  
<TemplateContent>  
    <ProjectItem ReplaceParameters="true">  
        Class1.cs  
    </ProjectItem>  
    ...  
</TemplateContent>  
```  
  
## См. также  
 [Настройка шаблонов](../ide/customizing-project-and-item-templates.md)