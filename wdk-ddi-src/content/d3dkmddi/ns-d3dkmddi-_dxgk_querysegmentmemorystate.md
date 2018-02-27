---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTMEMORYSTATE
title: "_DXGK_QUERYSEGMENTMEMORYSTATE"
author: windows-driver-content
description: DXGK_QUERYSEGMENTMEMORYSTATE is used with DxgkDdiQueryAdapterInfo to query invalid graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_querysegmentmemorystate.htm
old-project: display
ms.assetid: 565D8D8D-6EBB-4303-8F7E-E2A4B1DAE4EA
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_QUERYSEGMENTMEMORYSTATE
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYSEGMENTMEMORYSTATE, DXGK_SEGMENTMEMORYSTATE
---

# _DXGK_QUERYSEGMENTMEMORYSTATE structure


## -description


<b>DXGK_QUERYSEGMENTMEMORYSTATE</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> to query invalid graphics processing unit (GPU) memory ranges.


## -syntax


````
typedef struct _DXGK_QUERYSEGMENTMEMORYSTATE {
  WORD             DriverSegmentId;
  WORD             PhysicalAdapterIndex;
  UINT             NumInvalidMemoryRanges;
  DXGK_MEMORYRANGE *pMemoryRanges;
} DXGK_QUERYSEGMENTMEMORYSTATE;
````


## -struct-fields




### -field DriverSegmentId

A  1-based segment identifier of a local GPU memory segment.


### -field PhysicalAdapterIndex

Physical adapter index in a linked display adapter link.


### -field NumInvalidMemoryRanges

The number of entries in the <b>pMemoryRanges</b> array. This is the value returned by the kernel mode driver in <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor4.md">DXGK_SEGMENTDESCRIPTOR4</a>.


### -field pMemoryRanges

Array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a> structures for the invalid memory ranges.


## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor4.md">DXGK_SEGMENTDESCRIPTOR4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYSEGMENTMEMORYSTATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

