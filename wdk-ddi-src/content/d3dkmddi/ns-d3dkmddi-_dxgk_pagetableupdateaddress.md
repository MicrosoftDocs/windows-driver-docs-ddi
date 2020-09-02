---
UID: NS:d3dkmddi._DXGK_PAGETABLEUPDATEADDRESS
title: _DXGK_PAGETABLEUPDATEADDRESS (d3dkmddi.h)
description: DXGK_PAGETABLEUPDATEADDRESS contains the address of a page table to update. The member containing the address is defined as part of a DxgkDdiBuildPagingBuffer operation in the DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure.
old-location: display\dxgk_pagetableupdateaddress.htm
ms.assetid: 39013276-C76A-4E31-80DD-26C17A020BD6
ms.date: 05/10/2018
keywords: ["DXGK_PAGETABLEUPDATEADDRESS structure"]
ms.keywords: DXGK_PAGETABLEUPDATEADDRESS, DXGK_PAGETABLEUPDATEADDRESS structure [Display Devices], _DXGK_PAGETABLEUPDATEADDRESS, d3dkmddi/DXGK_PAGETABLEUPDATEADDRESS, display.dxgk_pagetableupdateaddress
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
req.typenames: DXGK_PAGETABLEUPDATEADDRESS
f1_keywords:
 - _DXGK_PAGETABLEUPDATEADDRESS
 - d3dkmddi/_DXGK_PAGETABLEUPDATEADDRESS
 - DXGK_PAGETABLEUPDATEADDRESS
 - d3dkmddi/DXGK_PAGETABLEUPDATEADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_PAGETABLEUPDATEADDRESS
---

# _DXGK_PAGETABLEUPDATEADDRESS structure


## -description

<b>DXGK_PAGETABLEUPDATEADDRESS</b> contains the address of a page table to update. The member containing the address is defined as part of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a> operation in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a> structure.

## -struct-fields

### -field CpuVirtual

The CPU virtual address of the page table to update.

### -field GpuPhysical

The GPU physical address of the page table to update.

### -field GpuVirtual

The GPU virtual address of the page table to update.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a>

