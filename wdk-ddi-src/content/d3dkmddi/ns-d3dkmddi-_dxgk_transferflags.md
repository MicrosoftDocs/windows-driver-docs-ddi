---
UID: NS:d3dkmddi._DXGK_TRANSFERFLAGS
title: "_DXGK_TRANSFERFLAGS"
author: windows-driver-content
description: The DXGK_TRANSFERFLAGS structure identifies the type of transfer operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_transferflags.htm
old-project: display
ms.assetid: b56657ac-98ff-482a-a2af-ffbfb8602248
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_TRANSFERFLAGS, DXGK_TRANSFERFLAGS structure [Display Devices], DmStructs_91973ccf-775f-4e97-bb1a-17cd1343a4f8.xml, _DXGK_TRANSFERFLAGS, d3dkmddi/DXGK_TRANSFERFLAGS, display.dxgk_transferflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_TRANSFERFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_TRANSFERFLAGS
---

# _DXGK_TRANSFERFLAGS structure


## -description


The DXGK_TRANSFERFLAGS structure identifies the type of transfer operation to set up in a call to the <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> function. 


## -struct-fields




### -field Swizzle

[in] A UINT value that specifies whether the driver should swizzle the source to the destination during the transfer. Note that for multiple-level allocations (for example, MIP-map textures), the driver should swizzle all levels of the allocations. For more information about swizzling allocations, see <a href="https://msdn.microsoft.com/c9be52d9-36b2-4a0f-9629-01b31293af38">Locking Swizzled Allocations</a>.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Unswizzle

[in] A UINT value that specifies whether the driver should unswizzle the source to the destination during the transfer. Note that for multiple-level allocations (for example, MIP-map textures), the driver should unswizzle all levels of the allocations. For more information about swizzling allocations, see <a href="https://msdn.microsoft.com/c9be52d9-36b2-4a0f-9629-01b31293af38">Locking Swizzled Allocations</a>.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field AllocationIsIdle

[in] A UINT value that specifies whether the graphics processing unit (GPU) is using the given allocation. If this member is set, the GPU is not using the given allocation; that is, no work was queued or will be queued to the GPU until the call to <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> returns.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field TransferStart

[in] A UINT value that specifies whether the transfer operation is starting. If this member is set, the transfer operation is starting.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field TransferEnd

[in] A UINT value that specifies whether the transfer operation is ending. If this member is set, the transfer operation is ending.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.


#### - Value

[in] A member in the union that DXGK_TRANSFERFLAGS contains that can hold a 32-bit value that identifies the transfer-operation type.


## -remarks



You can set the transfer-operation type by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that DXGK_TRANSFERFLAGS contains.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a>
 

 

