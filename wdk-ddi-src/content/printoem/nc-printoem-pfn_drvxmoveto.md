---
UID: NC:printoem.PFN_DrvXMoveTo
title: PFN_DrvXMoveTo (printoem.h)
description: The DrvXMoveTo function is obsolete.
old-location: print\drvxmoveto.htm
tech.root: print
ms.assetid: 20bebaea-a542-4cdd-8661-4c452a50efe5
ms.date: 04/20/2018
ms.keywords: DrvXMoveTo, DrvXMoveTo callback function [Print Devices], PFN_DrvXMoveTo, PFN_DrvXMoveTo callback, print.drvxmoveto, print_obsoletefunctions_a9d1de5a-71ef-4533-ab48-5e56a113dfb9.xml, printoem/DrvXMoveTo
ms.topic: callback
f1_keywords:
 - "printoem/DrvXMoveTo"
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
- DrvXMoveTo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_DrvXMoveTo callback function


## -description


The <b>DrvXMoveTo</b> function is obsolete.

 Windows 2000 and later Unidrv plug-ins should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvxmoveto">IPrintOemDriverUni::DrvXMoveTo</a>. 

This function pointer prototype defines the type of the <b>DrvXMoveTo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.


## -parameters




### -param pdevobj


### -param x


### -param dwFlags

