---
title: "Условия MSBuild | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, conditions
- conditions [MSBuild]
ms.assetid: 9d7aa308-b667-48ed-b4c9-a61e49eb0a85
caps.latest.revision: 14
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
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 87393579dd978ca512fe4bc8a0692502e224d202
ms.lasthandoff: 02/22/2017

---
# <a name="msbuild-conditions"></a>Условия MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] поддерживает определенный набор условий, которые можно применять везде, где разрешен атрибут `Condition`. В следующей таблице описаны эти условия.  
  
|Условие|Описание|  
|---------------|-----------------|  
|'`stringA`' == '`stringB`'|Принимает значение `true`, если `stringA` равна `stringB`.<br /><br /> Пример:<br /><br /> `Condition="'$(CONFIG)'=='DEBUG'"`<br /><br /> Одинарные кавычки можно не применять для простой последовательности букв и цифр или логических значений. Но они необходимы для пустых значений.|  
|'`stringA`' != '`stringB`'|Принимает значение `true`, если `stringA` не равна `stringB`.<br /><br /> Пример:<br /><br /> `Condition="'$(CONFIG)'!='DEBUG'"`<br /><br /> Одинарные кавычки можно не применять для простой последовательности букв и цифр или логических значений. Но они необходимы для пустых значений.|  
|\<, >, \<=, >=|Проверяет числовые значения операндов. Возвращает `true`, если отношение справедливо. Значения операндов могут быть десятичными или шестнадцатеричными числами. Шестнадцатеричные числа должны начинаться с "0x". **Примечание.** В XML символы `<` и `>` следует записывать в виде escape-последовательностей. Символ `<` представляется в виде `<`. Символ `>` представляется в виде `>`.|  
|Exists('`stringA`')|Принимает значение `true`, если файл или папка с именем `stringA` существует.<br /><br /> Пример:<br /><br /> `Condition="!Exists('$(builtdir)')"`<br /><br /> Одинарные кавычки можно не применять для простой последовательности букв и цифр или логических значений. Но они необходимы для пустых значений.|  
|HasTrailingSlash('`stringA`')|Принимает значение `true`, если указанная строка содержит завершающий символ обратной косой черты (\\) или символ прямой косой черты (/).<br /><br /> Пример:<br /><br /> `Condition="!HasTrailingSlash('$(OutputPath)')"`<br /><br /> Одинарные кавычки можно не применять для простой последовательности букв и цифр или логических значений. Но они необходимы для пустых значений.|  
|!|Принимает значение `true`, если операнд имеет значение `false`.|  
|И|Принимает значение `true`, если оба операнда имеют значение `true`.|  
|Или|Принимает значение `true`, если по крайней мере один операнд имеет значение `true`.|  
|()|Механизм группирования. Результат принимает значение `true`, если выражения, содержащиеся внутри, имеют значение `true`.|  
|$if$ (%expression%), $else$, $endif$|Проверяет, равняется ли значение указанного `%expression%` строковому значению переданного параметра пользовательского шаблона. Если результат проверки условия `$if$` принимает значение `true`, его операторы выполняются, в противном случае проверяется условие `$else$`. Если результат проверки условия `$else$` принимает значение `true`, его операторы выполняются, в противном случае условие `$endif$` завершает проверку выражений.<br /><br /> Примеры использования см. в разделе [Логика параметра-шаблона проекта или элемента Visual Studio](http://stackoverflow.com/questions/6709057/visual-studio-project-item-template-parameter-logic).|  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)   
 [Условные конструкции](../msbuild/msbuild-conditional-constructs.md)   
 [Пошаговое руководство. Создание файла проекта MSBuild с нуля](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)