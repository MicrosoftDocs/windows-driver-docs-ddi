---
UID: NF:printoem.OEMLineTo
title: OEMLineTo function
author: windows-driver-content
description: The OEMLineTo function draws a single, solid, integer-only cosmetic line.
old-location: print\oemlineto.htm
old-project: print
ms.assetid: 4131f7eb-de96-42cd-87f0-15fd73836a2d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OEMLineTo function [Print Devices], print_unidrv-pscript_rendering_45398181-47db-43c2-8c68-000dbf9cce8d.xml, OEMLineTo, print.oemlineto, printoem/OEMLineTo
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
-	OEMLineTo
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMLineTo function


## -description


The <code>OEMLineTo</code> function draws a single, solid, integer-only cosmetic line.


## -syntax


````
BOOL APIENTRY OEMLineTo(
   SURFOBJ  *pso,
   CLIPOBJ  *pco,
   BRUSHOBJ *pbo,
   LONG     x1,
   LONG     y1,
   LONG     x2,
   LONG     y2,
   RECTL    *prclBounds,
   MIX      mix
);
````


## -parameters




### -param pso



### -param pco



### -param pbo



### -param x1



### -param y1



### -param x2



### -param y2



### -param prclBounds



### -param mix


