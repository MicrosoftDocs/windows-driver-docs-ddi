---
UID: NC:printoem.PFN_DrvWriteAbortBuf
title: PFN_DrvWriteAbortBuf (printoem.h)
description: The DrvWriteAbortBuf function is obsolete.
old-location: print\drvwriteabortbuf.htm
tech.root: print
ms.date: 04/20/2018
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
 - DrvWriteAbortBuf
---

# PFN_DrvWriteAbortBuf callback function


## -description

The <b>DrvWriteAbortBuf</b> function is obsolete.

Windows 2000 and later Unidrv render plug-ins should use <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf">IPrintOemDriverUni::DrvWriteAbortBuf</a>. 

This function pointer prototype defines the type of the <b>DrvWriteAbortBuf</b> member of the <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.

## -parameters

### -param pdevobj

### -param pBuffer

### -param cbSize

### -param dwWait
