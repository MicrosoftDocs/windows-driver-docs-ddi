---
UID: NS:d3dkmddi._DXGK_MEMORYRANGE
title: _DXGK_MEMORYRANGE (d3dkmddi.h)
description: DXGK_MEMORYRANGE is used with DxgkDdiQueryAdapterInfo and DXGK_QUERYSEGMENTMEMORYSTATE to query bad graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_memoryrange.htm
ms.assetid: 68B9465D-BA5E-4DE3-8A55-B344399FBB5F
ms.date: 05/10/2018
keywords: ["_DXGK_MEMORYRANGE structure"]
ms.keywords: DXGK_MEMORYRANGE, DXGK_MEMORYRANGE structure [Display Devices], _DXGK_MEMORYRANGE, d3dkmddi/DXGK_MEMORYRANGE, display.dxgk_memoryrange
f1_keywords:
 - "d3dkmddi/DXGK_MEMORYRANGE"
 - "DXGK_MEMORYRANGE"
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
- DXGK_MEMORYRANGE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MEMORYRANGE
---

# _DXGK_MEMORYRANGE structure


## -description


<b>DXGK_MEMORYRANGE</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentmemorystate">DXGK_QUERYSEGMENTMEMORYSTATE</a> to query bad graphics processing unit (GPU) memory ranges.

The query is done during adapter object initialization. The driver will be called only if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor4">DXGK_SEGMENTDESCRIPTOR4</a>::<b>NumInvalidMemoryRanges</b> is not zero for a segment.
  


## -struct-fields




### -field SegmentOffset

The offset from the start of the segment in bytes. The value must be aligned to the segment page boundary.


### -field SizeInBytes

The number of byte in the range. The value must be multiple of the segment page size.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_querysegmentmemorystate">DXGK_QUERYSEGMENTMEMORYSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor4">DXGK_SEGMENTDESCRIPTOR4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>
 

 

