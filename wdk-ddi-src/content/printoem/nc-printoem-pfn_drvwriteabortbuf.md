---
UID: NC:printoem.PFN_DrvWriteAbortBuf
title: PFN_DrvWriteAbortBuf (printoem.h)
description: The DrvWriteAbortBuf function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvWriteAbortBuf callback function"]
ms.keywords: DrvWriteAbortBuf, DrvWriteAbortBuf callback function [Print Devices], PFN_DrvWriteAbortBuf, PFN_DrvWriteAbortBuf callback, print.drvwriteabortbuf, print_obsoletefunctions_016b6fea-c0ac-47ad-8834-5681e2f4de3d.xml, printoem/DrvWriteAbortBuf
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
 - PFN_DrvWriteAbortBuf
 - printoem/PFN_DrvWriteAbortBuf
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvWriteAbortBuf
---

## -description

The **DrvWriteAbortBuf** function is obsolete.

Windows 2000 and later Unidrv render plug-ins should use [IPrintOemDriverUni::DrvWriteAbortBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf). 

This function pointer prototype defines the type of the **DrvWriteAbortBuf** member of the [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs) structure.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param pBuffer

Defines the **PVOID** parameter *pBuffer*.

### -param cbSize

Defines the **DWORD** parameter *cbSize*.

### -param dwWait

Defines the **DWORD** parameter *dwWait*.

## -returns

Returns a **DWORD** value.
