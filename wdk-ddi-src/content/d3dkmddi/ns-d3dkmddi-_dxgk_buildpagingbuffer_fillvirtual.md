---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
title: _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL (d3dkmddi.h)
description: DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL is used as part of an operation to fill an allocation with a pattern.
old-location: display\dxgk_buildpagingbuffer_fillvirtual.htm
ms.assetid: 373065F6-C754-4517-905E-86A974866120
ms.date: 05/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL, DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL, d3dkmddi/DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL, display.dxgk_buildpagingbuffer_fillvirtual
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
---

# _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL</b> is used as part of an operation to fill an allocation with a pattern.


## -struct-fields




### -field hAllocation

The kernel mode driver handle of the allocation being filled. The handle is returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>. The allocation properties are needed in order to detect if the allocation is swizzled.


### -field AllocationOffsetInBytes

The offset, in bytes, from the start of the allocation being filled.


### -field FillSizeInBytes

The number of bytes to fill.


### -field FillPattern

The byte pattern to fill with.


### -field DestinationVirtualAddress

The virtual address of the destination in the context of the paging process.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>
 

 

