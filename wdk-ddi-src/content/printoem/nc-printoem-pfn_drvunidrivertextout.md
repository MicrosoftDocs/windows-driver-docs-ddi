---
UID: NC:printoem.PFN_DrvUnidriverTextOut
title: PFN_DrvUnidriverTextOut
author: windows-driver-content
description: The DrvUnidriverTextOut function is obsolete.
old-location: print\drvunidrivertextout.htm
old-project: print
ms.assetid: 72ba09b2-a889-439d-bbf2-ee6f9ebf5535
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.drvunidrivertextout, PFN_DrvUnidriverTextOut callback function [Print Devices], PFN_DrvUnidriverTextOut, printoem/PFN_DrvUnidriverTextOut, print_obsoletefunctions_eeb13110-561c-4c0f-912b-1a3a1cebd846.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: printoem.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	printoem.h
apiname:
-	PFN_DrvUnidriverTextOut
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# PFN_DrvUnidriverTextOut callback


## -description


The <b>DrvUnidriverTextOut</b> function is obsolete.

Windows 2000 and later printer drivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553132">IPrintOemDriverUni::DrvUniTextOut</a>. 

This function pointer prototype defines the type of the <b>DrvUnidriverTextOut</b> member of the <a href="..\printoem\ns-printoem-_drvprocs.md">DRVPROCS</a> structure.


## -prototype


````
 PFN_DrvUnidriverTextOut;

typedef BOOL APIENTRY* PFN_DrvUnidriverTextOut(
   SURFOBJ  *pso,
   STROBJ   *pstro,
   FONTOBJ  *pfo,
   CLIPOBJ  *pco,
   RECTL    *prclExtra,
   RECTL    *prclOpaque,
   BRUSHOBJ *pboFore,
   BRUSHOBJ *pboOpaque,
   POINTL   *pptlBrushOrg,
   MIX      mix
)
{ ... }
````


## -parameters




### -param *pso


### -param *pstro


### -param *pfo


### -param *pco


### -param *prclExtra


### -param *prclOpaque


### -param *pboFore


### -param *pboOpaque


### -param *pptlBrushOrg


### -param mix

