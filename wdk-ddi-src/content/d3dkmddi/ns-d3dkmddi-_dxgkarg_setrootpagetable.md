---
UID: NS:d3dkmddi._DXGKARG_SETROOTPAGETABLE
title: _DXGKARG_SETROOTPAGETABLE (d3dkmddi.h)
description: DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkarg_setrootpagetable.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_SETROOTPAGETABLE structure"]
ms.keywords: DXGKARG_SETROOTPAGETABLE, DXGKARG_SETROOTPAGETABLE structure [Display Devices], _DXGKARG_SETROOTPAGETABLE, d3dkmddi/DXGKARG_SETROOTPAGETABLE, display.dxgkarg_setrootpagetable
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.typenames: DXGKARG_SETROOTPAGETABLE
f1_keywords:
 - _DXGKARG_SETROOTPAGETABLE
 - d3dkmddi/_DXGKARG_SETROOTPAGETABLE
 - DXGKARG_SETROOTPAGETABLE
 - d3dkmddi/DXGKARG_SETROOTPAGETABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETROOTPAGETABLE
 - DXGKARG_SETROOTPAGETABLE
---

# _DXGKARG_SETROOTPAGETABLE structure


## -description

<b>DXGKARG_SETROOTPAGETABLE</b> is used by the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setrootpagetable">DxgkDdiSetRootPageTable</a>device driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.

## -struct-fields

### -field hContext

A context handle returned by <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>.

### -field Address

The GPU physical address of the root page table.

### -field NumEntries

 The root page table size in entries. GPU should generate invalid fault when a virtual address has a top level page table entry index, which is greater or equal this value.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setrootpagetable">DxgkDdiSetRootPageTable</a>

