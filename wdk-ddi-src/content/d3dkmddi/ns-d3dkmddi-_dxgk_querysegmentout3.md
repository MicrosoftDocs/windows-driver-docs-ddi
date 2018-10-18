---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTOUT3
title: "_DXGK_QUERYSEGMENTOUT3"
author: windows-driver-content
description: Describes memory-segment information that a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentout3.htm
ms.assetid: 4a78a998-7eab-4499-a280-96ca6d6ff5a2
ms.date: 5/10/2018
ms.keywords: DXGK_QUERYSEGMENTOUT3, DXGK_QUERYSEGMENTOUT3 structure [Display Devices], _DXGK_QUERYSEGMENTOUT3, d3dkmddi/DXGK_QUERYSEGMENTOUT3, display.dxgk_querysegmentout3
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_QUERYSEGMENTOUT3
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYSEGMENTOUT3
---

# _DXGK_QUERYSEGMENTOUT3 structure


## -description


Describes memory-segment information that a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver should return from a call to its <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


## -struct-fields




### -field NbSegment

[out] The number of memory segments that the driver supports.


### -field pSegmentDescriptor

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464086">DXGK_SEGMENTDESCRIPTOR3</a> structures that the driver populates with information about the segments it supports. The size of the array is the value that <b>NbSegment</b> specifies.


### -field PagingBufferSegmentId

[out] The identifier of the segment that the video memory manager should allocate the paging buffer from. This segment must be an aperture segment.


### -field PagingBufferSize

[out] The size, in bytes, that the video memory manager should allocate for the paging buffer.


### -field PagingBufferPrivateDataSize

[out] The size, in bytes, of the driver-resident private data structure that is associated with each paging buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero for <b>PagingBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a paging buffer is initialized to zero when the paging buffer is created. During the lifetime of the paging buffer, the video memory manager never accesses the private data structure that is associated with the paging buffer.


## -remarks



This structure is used by the  display miniport driver to return information about memory segments in response to a <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function call in which the graphics subsystem specifies the <b>DXGKQAITYPE_QUERYSEGMENT3</b> value in the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a> structure.

The video memory manager allocates a paging buffer either from an aperture segment (if the <b>PagingBufferSegmentId</b> member identifies the segment) or as a contiguous write-combined memory block (if <b>PagingBufferSegmentId</b> is set to 0). If <b>PagingBufferSegmentId</b> is set to 0, the GPU must access direct memory access (DMA) buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562015">DXGK_QUERYSEGMENTIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464086">DXGK_SEGMENTDESCRIPTOR3</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

