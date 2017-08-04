---
title: "Практическое руководство. Изменение пространства имен доменного языка | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Доменный язык, пространство имен"
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: 19
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 19
---
# Практическое руководство. Изменение пространства имен доменного языка
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Можно изменить пространство имен доменного языка.  Необходимо внести изменения в **Обозреватель DSL**в свойствах проекта пакета Dsl, и в информации о сборке.  
  
### Изменить пространство имен доменного языка  
  
1.  IN **Обозреватель DSL**щелкните  **DSL** узел.  
  
2.  в **Свойства** окно, изменяет  **Пространство имен** свойство.  
  
3.  Сохраните решение и convert шаблоны.  
  
4.  На **Проект** меню выберите команду  **Свойства Dsl**.  
  
     Свойства проекта.  
  
5.  Перейдите на вкладку **Приложение**.  
  
6.  Изменение **пространство имен по умолчанию** свойство к новому имени пространства имен.  
  
7.  Если также требуется изменить имя сборки, измените **Свойство имени сборки.**  
  
8.  При изменении имени сборки, открытое DslPackage \\ Package.tt и обновляет эта линия.  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. Если написан любой пользовательский код, убедитесь, изменить ссылки на пространства имен и класса в файлах кода.  
  
10. Сбросить экземпляр Visual Studio экспериментальном.  
  
    1.  Удалить **\\Users\\***{имя}***\\AppData\\Local\\Microsoft\\VisualStudio\\\*Exp**  
  
    2.  Об окнах **Запуск** выберите меню  **Все программы**"  **Пакет SDK для Visual Studio 2010**"  **Сервис**"  **Сбросить экспериментальном экземпляр**.  
  
11. На **Построение** выберите меню  **Перестроить решение**.  
  
## См. также  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ru-ru/ca5e84cb-a315-465c-be24-76aa3df276aa)