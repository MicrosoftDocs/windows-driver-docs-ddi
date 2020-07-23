---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_FLUSHTLB
title: _DXGK_BUILDPAGINGBUFFER_FLUSHTLB (d3dkmddi.h)
description: DXGK_BUILDPAGINGBUFFER_FLUSHTLB is used as part of a flush translation look-aside buffer (TLB) operation.
old-location: display\dxgk_buildpagingbuffer_flushtlb.htm
ms.assetid: 9FDE47A4-1784-41EB-9F60-76368D6DFEED
ms.date: 05/10/2018
keywords: ["_DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure"]
ms.keywords: DXGK_BUILDPAGINGBUFFER_FLUSHTLB, DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_FLUSHTLB, d3dkmddi/DXGK_BUILDPAGINGBUFFER_FLUSHTLB, display.dxgk_buildpagingbuffer_flushtlb
f1_keywords:
 - "d3dkmddi/DXGK_BUILDPAGINGBUFFER_FLUSHTLB"
 - "DXGK_BUILDPAGINGBUFFER_FLUSHTLB"
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
- DXGK_BUILDPAGINGBUFFER_FLUSHTLB
targetos: Windows
tech.root: display
req.typenames: DXGK_BUILDPAGINGBUFFER_FLUSHTLB
---

# _DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_FLUSHTLB</b> is used as part of a flush translation look-aside buffer (TLB) operation.


## -struct-fields




### -field RootPageTableAddress

Physical address of the root page table being invalidated.


### -field hProcess

KMD process handle,  returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>, that the page table belongs to. 


### -field StartVirtualAddress

The start of the affected GPU virtual address range.


### -field EndVirtualAddress

The end of the affected GPU virtual address range. When both <b>StartVirtualAddress</b> and <b>EndVirtualAddress</b> are zero, the entire GPU virtual address range is affected.

