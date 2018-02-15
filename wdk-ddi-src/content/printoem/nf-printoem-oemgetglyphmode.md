---
UID: NF:printoem.OEMGetGlyphMode
title: OEMGetGlyphMode function
author: windows-driver-content
description: The OEMGetGlyphMode function informs the GDI how to cache glyph information.
old-location: print\oemgetglyphmode.htm
old-project: print
ms.assetid: 350fe500-997b-48bb-90e2-04f39a7de3d2
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMGetGlyphMode function [Print Devices], print_unidrv-pscript_rendering_b5456727-fde5-4e4a-ae76-a5f571232325.xml, OEMGetGlyphMode, printoem/OEMGetGlyphMode, print.oemgetglyphmode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMGetGlyphMode
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMGetGlyphMode function


## -description


The <code>OEMGetGlyphMode</code> function informs the GDI how to cache glyph information.


## -syntax


````
ULONG APIENTRY OEMGetGlyphMode(
   DHPDEV  dhpdev,
   FONTOBJ *pfo
);
````


## -parameters




### -param dhpdev


### -param pfo

