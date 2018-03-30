---
UID: NS:d3dkmddi._DXGK_MEMORYRANGE
title: "_DXGK_MEMORYRANGE"
author: windows-driver-content
description: DXGK_MEMORYRANGE is used with DxgkDdiQueryAdapterInfo and DXGK_QUERYSEGMENTMEMORYSTATE to query bad graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_memoryrange.htm
old-project: display
ms.assetid: 68B9465D-BA5E-4DE3-8A55-B344399FBB5F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_MEMORYRANGE, DXGK_MEMORYRANGE structure [Display Devices], _DXGK_MEMORYRANGE, d3dkmddi/DXGK_MEMORYRANGE, display.dxgk_memoryrange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MEMORYRANGE
product: Windows
targetos: Windows
req.typenames: DXGK_MEMORYRANGE
---

# _DXGK_MEMORYRANGE structure


## -description


<b>DXGK_MEMORYRANGE</b> is used with <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn906839">DXGK_QUERYSEGMENTMEMORYSTATE</a> to query bad graphics processing unit (GPU) memory ranges.

The query is done during adapter object initialization. The driver will be called only if <a href="https://msdn.microsoft.com/library/windows/hardware/dn906842">DXGK_SEGMENTDESCRIPTOR4</a>::<b>NumInvalidMemoryRanges</b> is not zero for a segment.
  


## -struct-fields




### -field SegmentOffset

The offset from the start of the segment in bytes. The value must be aligned to the segment page boundary.


### -field SizeInBytes

The number of byte in the range. The value must be multiple of the segment page size.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906839">DXGK_QUERYSEGMENTMEMORYSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906842">DXGK_SEGMENTDESCRIPTOR4</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

