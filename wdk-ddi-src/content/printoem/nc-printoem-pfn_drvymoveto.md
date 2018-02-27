---
UID: NC:printoem.PFN_DrvYMoveTo
title: PFN_DrvYMoveTo
author: windows-driver-content
description: The DrvYMoveTo function is obsolete.
old-location: print\drvymoveto.htm
old-project: print
ms.assetid: 0d8539eb-0b9c-4aae-abbe-bb7ddd6231f5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvYMoveTo, DrvYMoveTo callback function [Print Devices], PFN_DrvYMoveTo, print.drvymoveto, print_obsoletefunctions_90e3798e-8acd-4aad-a3a2-ae8a84934a92.xml, printoem/DrvYMoveTo
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	printoem.h
api_name:
-	DrvYMoveTo
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# PFN_DrvYMoveTo callback


## -description


The <b>DrvYMoveTo</b> function is obsolete.

Windows 2000 and later Unidrv plug-ins should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553144">IPrintOemDriverUni::DrvYMoveTo</a>. 

This function pointer prototype defines the type of the <b>DrvYMoveTo</b> member of the <a href="..\printoem\ns-printoem-_drvprocs.md">DRVPROCS</a> structure.


## -prototype


````
PFN_DrvYMoveTo DrvYMoveTo;

 INT APIENTRY* DrvYMoveTo(
   PDEVOBJ pdevobj,
   INT     y,
   DWORD   dwFlags
)
{ ... }
````


## -parameters




### -param pdevobj


### -param y


### -param dwFlags

