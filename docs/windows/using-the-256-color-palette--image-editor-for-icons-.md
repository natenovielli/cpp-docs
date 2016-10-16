---
title: "Using the 256-Color Palette (Image Editor for Icons)"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "256-color palette"
  - "colors, icons and cursors"
  - "cursors, color"
  - "color palettes, 256-color"
  - "palettes, 256-color"
  - "icons, color"
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
caps.latest.revision: 7
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Using the 256-Color Palette (Image Editor for Icons)
To draw with a selection from the 256-color palette, you need to select the colors from the Colors palette in the [Colors window](../windows/colors-window--image-editor-for-icons-.md).  
  
### To choose a color from the 256-color palette for large icons  
  
1.  Select the large icon or cursor, or create a new large icon or cursor.  
  
2.  Choose a color from the 256 colors displayed in the **Colors** palette in the **Colors** window.  
  
     The color selected will become the current color in the colors palette in the **Colors** window.  
  
    > [!NOTE]
    >  The initial palette used for 256-color images matches the palette returned by the CreateHalftonePalette Windows API. All icons intended for the Windows shell should use this palette to prevent flicker during palette realization.  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Localizing Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) and [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Requirements  
  
 None  
  
## See Also  
 [Accelerator Keys](../mfc/accelerator-keys--image-editor-for-icons-.md)   
 [Creating a 256-Color Icon or Cursor](../mfc/creating-a-256-color-icon-or-cursor--image-editor-for-icons-.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors--image-resources-for-display-devices--image-editor-for-icons-.md)