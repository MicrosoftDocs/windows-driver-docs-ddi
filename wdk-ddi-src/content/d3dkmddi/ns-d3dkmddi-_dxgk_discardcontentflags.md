---
UID: NS:d3dkmddi._DXGK_DISCARDCONTENTFLAGS
title: _DXGK_DISCARDCONTENTFLAGS (d3dkmddi.h)
description: The DXGK_DISCARDCONTENTFLAGS structure identifies the type of discard-content operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_discardcontentflags.htm
ms.assetid: 0a93d3a2-0274-4b14-9c4b-9ed31a48e600
ms.date: 05/10/2018
keywords: ["DXGK_DISCARDCONTENTFLAGS structure"]
ms.keywords: DXGK_DISCARDCONTENTFLAGS, DXGK_DISCARDCONTENTFLAGS structure [Display Devices], DmStructs_9ff479c6-8592-4ebd-b001-c0a7d58772f2.xml, _DXGK_DISCARDCONTENTFLAGS, d3dkmddi/DXGK_DISCARDCONTENTFLAGS, display.dxgk_discardcontentflags
f1_keywords:
 - "d3dkmddi/DXGK_DISCARDCONTENTFLAGS"
 - "DXGK_DISCARDCONTENTFLAGS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
- DXGK_DISCARDCONTENTFLAGS
targetos: Windows
tech.root: display
req.typenames: DXGK_DISCARDCONTENTFLAGS
---

# _DXGK_DISCARDCONTENTFLAGS structure


## -description


The DXGK_DISCARDCONTENTFLAGS structure identifies the type of discard-content operation to set up in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a> function. 


## -struct-fields




### -field AllocationIsIdle

[in] A UINT value that specifies whether the allocation that is referenced in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a> is idle. If this member is not set, the driver should determine that the allocation is either currently busy or might become busy. If this member is set, the video memory manager guarantees that the allocation remains idle for the duration of the call to <i>DxgkDdiBuildPagingBuffer</i>.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that DXGK_DISCARDCONTENTFLAGS contains that can hold a 32-bit value that identifies the discard-content-operation type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a>
 

 

