---
UID: NC:printoem.PFN_DrvWriteSpoolBuf
title: PFN_DrvWriteSpoolBuf (printoem.h)
description: The DrvWriteSpoolBuf function pointed to by this function pointer is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvWriteSpoolBuf callback function"]
ms.keywords: DrvWriteSpoolBuf, DrvWriteSpoolBuf callback function [Print Devices], PFN_DrvWriteSpoolBuf, PFN_DrvWriteSpoolBuf callback, print.drvwritespoolbuf, print_obsoletefunctions_06e6fe98-5851-4c2e-863a-5afe735321fb.xml, printoem/DrvWriteSpoolBuf
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
 - PFN_DrvWriteSpoolBuf
 - printoem/PFN_DrvWriteSpoolBuf
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvWriteSpoolBuf
---

## -description

The **DrvWriteSpoolBuf** function pointed to by this function pointer is obsolete.

 Windows 2000 and later render plug-ins should use [IPrintOemDriverUni::DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf) (Unidrv plug-ins), [IPrintOemDriverPS::DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverps-drvwritespoolbuf) (Pscript plug-ins), or [IPrintCorePS2::DrvWriteSpoolBuf](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcoreps2-drvwritespoolbuf) (Pscript plug-ins).

This function pointer prototype defines the **DrvWriteSpoolBuf** member of the [DRVPROCS](/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs) structure.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param pBuffer

Defines the **PVOID** parameter *pBuffer*.

### -param cbSize

Defines the **DWORD** parameter *cbSize*.

## -returns

Returns a **DWORD** value.
