---
title: 'Практическое: изменение языка публикации для приложения ClickOnce | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish language property
- ClickOnce deployment, changing publish language
- publishing, ClickOnce
ms.assetid: ef5024c4-cda1-4970-bc75-32a2a10c92c3
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 2330f234b5b00fdde99376fbe5664bd5dbd99551
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49239661"
---
# <a name="how-to-change-the-publish-language-for-a-clickonce-application"></a>Практическое руководство. Изменение языка публикации для приложения ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

При публикации [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] приложения, пользовательский интерфейс во время установки значения по умолчанию для языка и региональных параметров компьютера разработки. Если вы публикуете локализованного приложения, необходимо будет указать язык и региональные параметры, соответствующие локализованной версии. Это определяется параметром `Publish language` свойство проекта.  
  
 `Publish language` Может быть установлено **параметры публикации** окне доступен из **публикации** странице **конструктор проектов**.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-change-the-publish-language"></a>Чтобы изменить язык публикации  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  Нажмите кнопку **публикации** вкладки.  
  
3.  Нажмите кнопку **параметры** кнопку, чтобы открыть **параметры публикации** диалоговое окно.  
  
4.  Нажмите кнопку **описание**.  
  
5.  В **параметры публикации** диалоговое окно, выберите язык и язык и региональные параметры из **язык публикации** стрелку раскрывающегося списка и нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также  
 [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



