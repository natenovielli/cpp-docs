---
title: "Compiler Error CS0021"
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
  - "CS0021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0021"
ms.assetid: 4eb5fa24-8261-4962-b36a-224be5074217
caps.latest.revision: 14
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
# Compiler Error CS0021
Cannot apply indexing with [] to an expression of type 'type'  
  
 An attempt was made to access a value through an indexer on a data type that does not support [Indexers](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md).  
  
 You may get CS0021 when trying to use an indexer in a C++ assembly. In this case, decorate the C++ class with the `DefaultMember` attribute so the C# compiler knows which indexer is the default. The following sample generates CS0021.  
  
## Example  
 This file compiles to a .dll file—with the `DefaultMember` attribute commented out—in order to generate the error.  
  
```  
// CPP0021.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
// Uncomment the following line to resolve  
//[DefaultMember("myItem")]  
public ref class MyClassMC  
{  
        public:  
        property int myItem[int]  
        {  
            int get(int i){  return 5; }  
            void set(int i, int value) {}  
        }  
};  
```  
  
## Example  
 The following is the C# file that calls the .dll file. This file attempts to access the class via an indexer, but because no member was declared as the default indexer to be used, the error is generated.  
  
```  
// CS0021.cs  
// compile with: /reference:CPP0021.dll  
public class MyClass  
{  
    public static void Main()  
    {  
        MyClassMC myMC = new MyClassMC();  
        int j = myMC[1]; // CS0021  
    }  
}  
```