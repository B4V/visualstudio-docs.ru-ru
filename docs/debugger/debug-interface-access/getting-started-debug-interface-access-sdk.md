---
title: Приступая к работе (доступа к интерфейсу отладки пакета SDK) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e5cfcad351f19f48678d575e11b074375c6aaadc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49887300"
---
# <a name="getting-started-debug-interface-access-sdk"></a>Начало работы (SDK для доступа к интерфейсу отладки)
Debug Interface Access (DIA) пакет SDK предоставляет инструкции документацию и пример, в котором показано, как использовать API доступа к интерфейсу отладки. Используйте интерфейсы и методы в пакете SDK для доступа к интерфейсу отладки при разработке приложений, которые открывают файлы PDB-файл и .dbg и поиск по их содержимому для символов, значения, атрибутов, адресов и других отладочную информацию. Этот пакет SDK также предоставляет ссылочные таблицы для свойства, связанные с символами, которые встречаются в приложениях C++.  
  
 Чтобы лучше всего использовать пакет SDK для доступа к интерфейсу отладки, необходимо ознакомиться со следующим:  
  
- Язык программирования C++  
  
- Программирование COM  
  
- Visual Studio интегрированная среда разработки (IDE) для компиляции образцов  
  
  Пакет SDK для доступа к интерфейсу отладки, как правило, устанавливается с помощью Visual Studio и его расположение по умолчанию — *[диск]* \Program Files\Microsoft 9.0\DIA Visual Studio SDK. В процессе установки, msdia90.dll, реализующий пакет SDK для доступа к интерфейсу отладки, автоматически регистрируется, поэтому все, что необходимо сделать, чтобы использовать его для включения `dia2.h` в программе и ссылаться на `diaguids.lib`.  
  
  Заголовок: include\dia2.h  
  
  Библиотека: lib\diaguids.lib  
  
  Библиотеки DLL: bin\msdia80.dll  
  
  IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обзор набора средств Visual Studio для Unity](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 Просматривает базовая архитектура DIA.  
  
 [Запрос PDB-файла](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Содержит пошаговые инструкции по использованию API доступа к интерфейсу отладки для запроса PDB-файл.  
  
## <a name="see-also"></a>См. также  
 [SDK для доступа к интерфейсу отладки](../../debugger/debug-interface-access/debug-interface-access-sdk.md)