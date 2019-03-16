---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
title: _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES (d3dkmddi.h)
description: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES describes the operation used copy page table entries from one location to another.
old-location: display\dxgk_buildpagingbuffer_copypagetableentries.htm
ms.assetid: 627FB3E6-3C5D-4104-B129-08D3EC0B963E
ms.date: 05/10/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES, DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES, d3dkmddi/DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES, display.dxgk_buildpagingbuffer_copypagetableentries
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES
---

# _DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES</b> describes the operation used copy page table entries from one location to another. 


## -struct-fields




### -field NumRanges

The number of elements in the <b>pRanges</b> array.


### -field pRanges

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn894165">DXGK_BUILDPAGINGBUFFER_COPY_RANGE</a> structure describing each range of page table entries to copy.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894165">DXGK_BUILDPAGINGBUFFER_COPY_RANGE</a>
 

 

