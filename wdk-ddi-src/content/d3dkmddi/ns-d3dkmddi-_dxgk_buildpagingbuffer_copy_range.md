---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_COPY_RANGE
title: "_DXGK_BUILDPAGINGBUFFER_COPY_RANGE"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_COPY_RANGE is used as part of a page table entry copy operation.
old-location: display\dxgk_buildpagingbuffer_copy_range.htm
ms.assetid: BA35F50C-7399-41DC-A10B-2F5E4BB24B49
ms.date: 5/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_COPY_RANGE, DXGK_BUILDPAGINGBUFFER_COPY_RANGE structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_COPY_RANGE, d3dkmddi/DXGK_BUILDPAGINGBUFFER_COPY_RANGE, display.dxgk_buildpagingbuffer_copy_range
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
-	DXGK_BUILDPAGINGBUFFER_COPY_RANGE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_COPY_RANGE
---

# _DXGK_BUILDPAGINGBUFFER_COPY_RANGE structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_COPY_RANGE</b> is used as part of a page table entry copy operation.


## -struct-fields




### -field NumPageTableEntries

The number of page table entries to copy.


### -field SrcPageTableAddress

The virtual address of the source page table for the range. The address is aligned to 64KB boundary.


### -field DstPageTableAddress

The virtual address of the destination page table for the range. The address is aligned to 64KB boundary.


### -field SrcStartPteIndex

The index of the first page table entry in the source page table for the range.


### -field DstStartPteIndex

The index of the first page table entry in the destination page table for the range.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894164">DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES</a>
 

 

