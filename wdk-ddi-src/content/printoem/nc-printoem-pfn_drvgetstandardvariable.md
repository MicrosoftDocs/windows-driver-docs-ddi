---
UID: NC:printoem.PFN_DrvGetStandardVariable
title: PFN_DrvGetStandardVariable (printoem.h)
description: This DrvGetStandardVariable function is obsolete.
tech.root: print
ms.date: 08/11/2022
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
 - PFN_DrvGetStandardVariable
---

## -description

This **DrvGetStandardVariable** function is obsolete.

Windows 2000 and later printer drivers should use [IPrintOemDriverUni::DrvGetStandardVariable](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvgetstandardvariable).

This function pointer prototype defines the type of the **BGetStandardVariable** member of the [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs) structure.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param dwIndex

Defines the **DWORD** parameter *dwIndex*.

### -param pBuffer

Defines the **PVOID** parameter *pBuffer*.

### -param cbSize

Defines the **DWORD** parameter *cbSize*.

### -param pcbNeeded

Defines the **PDWORD** parameter *pcbNeeded*.

## -returns

Returns a **BOOL** value.
