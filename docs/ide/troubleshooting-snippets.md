---
title: Устранение неполадок с фрагментами
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 61485e50c61580b69c1dfcb5434849ea9122bde7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942339"
---
# <a name="troubleshoot-snippets"></a>Устранение неполадок с фрагментами

Проблемы с фрагментами кода IntelliSense обычно вызваны двумя причинами: поврежденный файл фрагмента или неправильное его содержимое.

## <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Не удается перетащить фрагмент кода из проводника в исходный файл Visual Studio

- Возможно, XML-код в файле фрагмента поврежден. **Редактор XML** в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяет найти нарушения структуры XML.

- Возможно, файл фрагмента не соответствует схеме фрагмента. **Редактор XML** в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяет найти нарушения структуры XML.

## <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>В коде есть невыделенные ошибки компилятора

-   Возможно, отсутствует ссылка на проект. Изучите документацию о фрагменте. Если ссылка на компьютере отсутствует, ее потребуется установить. Вставка фрагмента должна добавить в проект все необходимые ссылки. Если для фрагмента отсутствуют справочные сведения, об этой ошибке можно сообщить автору фрагмента.

-   Возможно, не определена переменная. Неопределенные переменные во фрагменте кода должны быть выделены. В противном случае об этой ошибке можно сообщить автору фрагмента.

## <a name="see-also"></a>См. также

- [Фрагменты кода](../ide/code-snippets.md)
