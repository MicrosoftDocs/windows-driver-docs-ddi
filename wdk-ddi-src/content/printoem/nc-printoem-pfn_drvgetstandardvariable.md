---
UID: NC:printoem.PFN_DrvGetStandardVariable
title: PFN_DrvGetStandardVariable (printoem.h)
description: This DrvGetStandardVariable function is obsolete.
old-location: print\drvgetstandardvariable.htm
tech.root: print
ms.assetid: 743d8e3c-3115-4c2d-b7f3-6f99ba684693
ms.date: 04/20/2018
keywords: ["PFN_DrvGetStandardVariable callback function"]
ms.keywords: DrvGetStandardVariable, DrvGetStandardVariable callback function [Print Devices], PFN_DrvGetStandardVariable, PFN_DrvGetStandardVariable callback, print.drvgetstandardvariable, print_obsoletefunctions_143de6bb-bea1-4292-8ac4-e34c2610a8ab.xml, printoem/DrvGetStandardVariable
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_DrvGetStandardVariable
 - printoem/PFN_DrvGetStandardVariable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - DrvGetStandardVariable
---

# PFN_DrvGetStandardVariable callback function


## -description

This <b>DrvGetStandardVariable</b> function is obsolete. 

Windows 2000 and later printer drivers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetstandardvariable">IPrintOemDriverUni::DrvGetStandardVariable</a>. 

This function pointer prototype defines the type of the <b>BGetStandardVariable</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.

## -parameters

### -param pdevobj

### -param dwIndex

### -param pBuffer

### -param cbSize

### -param pcbNeeded

