---
UID: NC:d3dkmddi.DXGKDDI_GETROOTPAGETABLESIZE
title: DXGKDDI_GETROOTPAGETABLESIZE (d3dkmddi.h)
description: DxgkDdiGetRootPageTableSize returns the minimum root page table size, in bytes, that is needed to hold the given number of page table entries.
old-location: display\dxgkddigetrootpagetablesize.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_GETROOTPAGETABLESIZE callback function"]
ms.keywords: DXGKDDI_GETROOTPAGETABLESIZE, DXGKDDI_GETROOTPAGETABLESIZE callback, DxgkDdiGetRootPageTableSize, DxgkDdiGetRootPageTableSize callback function [Display Devices], d3dkmddi/DxgkDdiGetRootPageTableSize, display.dxgkddigetrootpagetablesize
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_GETROOTPAGETABLESIZE
 - d3dkmddi/DXGKDDI_GETROOTPAGETABLESIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_GETROOTPAGETABLESIZE
product:
 - Windows
---

# DXGKDDI_GETROOTPAGETABLESIZE callback function


## -description

<b>DxgkDdiGetRootPageTableSize</b> returns the minimum root page table size,  in bytes, that is needed to hold the given number of page table entries. The actual number of entries in the page table could be greater than the given value. 

<b>DxgkDdiGetRootPageTableSize</b> is called only when <b>DXGK_GPUMMUCAPS</b>::<b>PageTableLevelCount</b> is two.

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pArgs

The <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_getrootpagetablesize">DXGKARG_GETROOTPAGETABLESIZE</a> structure that describes the operation.

## -returns

The page table size in bytes. The size must be a multiple of the page size of the GPU memory segment where page table is located.

