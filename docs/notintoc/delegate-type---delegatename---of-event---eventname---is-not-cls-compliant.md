---
title: "Delegate type &#39;&lt;delegatename&gt;&#39; of event &#39;&lt;eventname&gt;&#39; is not CLS-compliant"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc40050"
  - "vbc40050"
helpviewer_keywords: 
  - "BC40050"
ms.assetid: 92f5be26-9a82-46d4-bf97-005f2c7ca424
caps.latest.revision: 9
ms.author: "billchi"
manager: "douge"
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
# Delegate type &#39;&lt;delegatename&gt;&#39; of event &#39;&lt;eventname&gt;&#39; is not CLS-compliant
An [Event Statement](../Topic/Event%20Statement.md) uses a delegate to specify its signature, but the [Delegate Statement](../Topic/Delegate%20Statement.md) is marked as `<CLSCompliant(False)>` or is not marked.  
  
 When you apply the \<xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance. There is no default for this parameter, and you must supply a value.  
  
 If you do not apply \<xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.  
  
 By default, this message is a warning. For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Error ID:** BC40050  
  
### To correct this error  
  
-   If you require CLS compliance and have control over the definition of the delegate, apply \<xref:System.CLSCompliantAttribute> to its declaration to mark it as `<CLSCompliant(True)>`.  
  
-   If you do not have control over the definition of the delegate or cannot mark it as compliant, remove the \<xref:System.CLSCompliantAttribute> from the `Event` statement or mark it as `<CLSCompliant(False)>`.  
  
## See Also  
 [\<PAVE OVER> Writing CLS-Compliant Code](assetId:///4c705105-69a2-4e5e-b24e-0633bc32c7f3)