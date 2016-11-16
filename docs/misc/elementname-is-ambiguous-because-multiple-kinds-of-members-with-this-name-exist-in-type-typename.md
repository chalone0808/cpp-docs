---
title: "&#39;&lt;elementname&gt;&#39; is ambiguous because multiple kinds of members with this name exist in &lt;type&gt; &#39;&lt;typename&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31429"
  - "vbc31429"
helpviewer_keywords: 
  - "BC31429"
ms.assetid: fdc92c16-934d-47c0-9c44-332cbd58b73b
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# &#39;&lt;elementname&gt;&#39; is ambiguous because multiple kinds of members with this name exist in &lt;type&gt; &#39;&lt;typename&gt;&#39;
An expression accesses a programming element defined in a class, structure, module, or interface that contains more than one member with the same name.  
  
 The most likely cause of this error is *case sensitivity*. Visual Basic names are case-insensitive, which means you can capitalize them differently at different places in your code. For example, if you define a variable with the name `XYZ` and later access it as `xyz`, the compiler considers the two names to be equivalent.  
  
 However, other languages, such as [C#](/dotnet/csharp/csharp) and [Visual C++](../top/visual-cpp-in-visual-studio.md), are case-sensitive. In such a language, `XYZ` and `xyz` are not considered to be the same name. Therefore, a class written in such a language could define a variable named `XYZ` and a property named `xyz`. The common language runtime (CLR) preserves case sensitivity in assemblies. However, if a Visual Basic application accesses an assembly with names `XYZ` and `xyz`, they appear as the same name.  
  
 **Error ID:** BC31429  
  
### To correct this error  
  
1.  If you have control over the source code of the defining type, consider renaming the members so that they differ by more than only casing. This might not be possible if the defining type has already been published and is being used by other applications.  
  
2.  If you cannot rename the members in the defining type, remove the cited programming element from your code. You cannot access an element that appears to Visual Basic to have multiple definitions.  
  
## See Also  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Troubleshooting Variables](/dotnet/visual-basic/programming-guide/language-features/variables/troubleshooting-variables)   
 [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md)