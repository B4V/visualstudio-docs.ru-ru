---
title: "Разрешение вопросов, связанных с исключениями: System.ArgumentException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArgumentException - исключение"
  - "System.ArgumentException - исключение"
ms.assetid: d8052e62-bc73-4828-87e9-a84ef2a39a5b
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Разрешение вопросов, связанных с исключениями: System.ArgumentException
Исключение <xref:System.ArgumentException> возникает, если хотя бы один из передаваемых методу аргументов не соответствует спецификациям параметров данного метода.  
  
 В следующем примере кода показан вызов исключения, когда переданный методу `DivideByTwo` аргумент не является четным числом.  
  
```vb#  
Module Module1 Sub Main() ' ArgumentException is not thrown in DivideByTwo because 10 is ' an even number. Console.WriteLine("10 divided by 2 is {0}", DivideByTwo(10)) Try ' ArgumentException is thrown in DivideByTwo because 7 is ' not an even number. Console.WriteLine("7 divided by 2 is {0}", DivideByTwo(7)) Catch argEx As ArgumentException ' Tell the user which problem is encountered. Console.WriteLine("7 cannot be evenly divided by 2.") Console.WriteLine("Exception message: " & argEx.Message) End Try ' Uncomment the next statement to see what happens if you call ' DivideByTwo directly. 'Console.WriteLine(DivideByTwo(7)) End Sub Function DivideByTwo(ByVal num As Integer) As Integer ' If num is an odd number, throw an ArgumentException. The ' ArgumentException class provides a number of constructors ' that you can choose from. If num Mod 2 = 1 Then Throw New ArgumentException("Argument for num must be" & _ " an even number.") End If ' Value of num is even, so return half of its value. Return num / 2 End Function End Module  
```  
  
 Все экземпляры класса `ArgumentException` должны включать информацию, указывающую, какой аргумент не является допустимым, и каков диапазон допустимых значений. Если ситуации соответствует более точное исключение, такое как <xref:System.ArgumentNullException> или <xref:System.ArgumentOutOfRangeException>, следует использовать его вместо `ArgumentException`.  
  
 Дополнительные сведения об этом исключении, в том числе примеры кода на других языках, см. в разделе <xref:System.ArgumentException>. Список дополнительных конструкторов см. в разделе <xref:System.ArgumentException.%23ctor%2A>.  
  
## См. также  
 <xref:System.ArgumentException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)