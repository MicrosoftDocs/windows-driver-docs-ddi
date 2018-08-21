---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTMEMORYSTATE
title: "_DXGK_QUERYSEGMENTMEMORYSTATE"
author: windows-driver-content
description: DXGK_QUERYSEGMENTMEMORYSTATE is used with DxgkDdiQueryAdapterInfo to query invalid graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_querysegmentmemorystate.htm
ms.assetid: 565D8D8D-6EBB-4303-8F7E-E2A4B1DAE4EA
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_QUERYSEGMENTMEMORYSTATE, DXGK_QUERYSEGMENTMEMORYSTATE structure [Display Devices], DXGK_SEGMENTMEMORYSTATE, _DXGK_QUERYSEGMENTMEMORYSTATE, d3dkmddi/DXGK_QUERYSEGMENTMEMORYSTATE, display.dxgk_querysegmentmemorystate
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_QUERYSEGMENTMEMORYSTATE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_QUERYSEGMENTMEMORYSTATE, DXGK_SEGMENTMEMORYSTATE
---

# _DXGK_QUERYSEGMENTMEMORYSTATE structure


## -description


<b>DXGK_QUERYSEGMENTMEMORYSTATE</b> is used with <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> to query invalid graphics processing unit (GPU) memory ranges.


## -struct-fields




### -field DriverSegmentId

A  1-based segment identifier of a local GPU memory segment.


### -field PhysicalAdapterIndex

Physical adapter index in a linked display adapter link.


### -field NumUEFIFrameBufferRanges

 


### -field NumInvalidMemoryRanges

The number of entries in the <b>pMemoryRanges</b> array. This is the value returned by the kernel mode driver in <a href="https://msdn.microsoft.com/library/windows/hardware/dn906842">DXGK_SEGMENTDESCRIPTOR4</a>.


### -field pMemoryRanges

Array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn906829">DXGK_MEMORYRANGE</a> structures for the invalid memory ranges.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906829">DXGK_MEMORYRANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906842">DXGK_SEGMENTDESCRIPTOR4</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

