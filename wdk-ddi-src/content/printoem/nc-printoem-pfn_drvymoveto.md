---
UID: NC:printoem.PFN_DrvYMoveTo
title: PFN_DrvYMoveTo (printoem.h)
description: The DrvYMoveTo function is obsolete.
old-location: print\drvymoveto.htm
tech.root: print
ms.assetid: 0d8539eb-0b9c-4aae-abbe-bb7ddd6231f5
ms.date: 04/20/2018
keywords: ["PFN_DrvYMoveTo callback function"]
ms.keywords: DrvYMoveTo, DrvYMoveTo callback function [Print Devices], PFN_DrvYMoveTo, PFN_DrvYMoveTo callback, print.drvymoveto, print_obsoletefunctions_90e3798e-8acd-4aad-a3a2-ae8a84934a92.xml, printoem/DrvYMoveTo
f1_keywords:
 - "printoem/DrvYMoveTo"
 - "DrvYMoveTo"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- printoem.h
api_name:
- DrvYMoveTo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_DrvYMoveTo callback function


## -description


The <b>DrvYMoveTo</b> function is obsolete.

Windows 2000 and later Unidrv plug-ins should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvymoveto">IPrintOemDriverUni::DrvYMoveTo</a>. 

This function pointer prototype defines the type of the <b>DrvYMoveTo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.


## -parameters




### -param pdevobj


### -param y


### -param dwFlags

