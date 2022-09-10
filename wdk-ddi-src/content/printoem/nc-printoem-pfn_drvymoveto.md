---
UID: NC:printoem.PFN_DrvYMoveTo
title: PFN_DrvYMoveTo (printoem.h)
description: The DrvYMoveTo function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvYMoveTo callback function"]
ms.keywords: DrvYMoveTo, DrvYMoveTo callback function [Print Devices], PFN_DrvYMoveTo, PFN_DrvYMoveTo callback, print.drvymoveto, print_obsoletefunctions_90e3798e-8acd-4aad-a3a2-ae8a84934a92.xml, printoem/DrvYMoveTo
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_DrvYMoveTo
 - printoem/PFN_DrvYMoveTo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvYMoveTo
---

## -description

The **DrvYMoveTo** function is obsolete.

Windows 2000 and later Unidrv plug-ins should use [IPrintOemDriverUni::DrvYMoveTo](../prcomoem/nf-prcomoem-iprintoemdriveruni-drvymoveto.md).

This function pointer prototype defines the type of the **DrvYMoveTo** member of the [DRVPROCS](./ns-printoem-_drvprocs.md) structure.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param y

Defines the **INT** parameter *y*.

### -param dwFlags

Defines the **DWORD** parameter *dwFlags*.

## -returns

Returns a **INT** value.