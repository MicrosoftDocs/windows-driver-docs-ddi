---
UID: NC:printoem.PFN_DrvXMoveTo
title: PFN_DrvXMoveTo (printoem.h)
description: The DrvXMoveTo function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvXMoveTo callback function"]
ms.keywords: DrvXMoveTo, DrvXMoveTo callback function [Print Devices], PFN_DrvXMoveTo, PFN_DrvXMoveTo callback, print.drvxmoveto, print_obsoletefunctions_a9d1de5a-71ef-4533-ab48-5e56a113dfb9.xml, printoem/DrvXMoveTo
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
 - PFN_DrvXMoveTo
 - printoem/PFN_DrvXMoveTo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvXMoveTo
---

## -description

The **DrvXMoveTo** function is obsolete.

 Windows 2000 and later Unidrv plug-ins should use [IPrintOemDriverUni::DrvXMoveTo](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvxmoveto).

This function pointer prototype defines the type of the **DrvXMoveTo** member of the [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs) structure.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param x

Defines the **INT** parameter *x*.

### -param dwFlags

Defines the **DWORD** parameter *dwFlags*.

## -returns

Returns a **INT** value.
