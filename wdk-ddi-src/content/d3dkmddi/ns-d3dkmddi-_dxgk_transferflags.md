---
UID: NS:d3dkmddi._DXGK_TRANSFERFLAGS
title: "_DXGK_TRANSFERFLAGS"
author: windows-driver-content
description: The DXGK_TRANSFERFLAGS structure identifies the type of transfer operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_transferflags.htm
old-project: display
ms.assetid: b56657ac-98ff-482a-a2af-ffbfb8602248
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_TRANSFERFLAGS structure [Display Devices], display.dxgk_transferflags, _DXGK_TRANSFERFLAGS, d3dkmddi/DXGK_TRANSFERFLAGS, DXGK_TRANSFERFLAGS, DmStructs_91973ccf-775f-4e97-bb1a-17cd1343a4f8.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_TRANSFERFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_TRANSFERFLAGS
---

# _DXGK_TRANSFERFLAGS structure


## -description


The DXGK_TRANSFERFLAGS structure identifies the type of transfer operation to set up in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function. 


## -syntax


````
typedef struct _DXGK_TRANSFERFLAGS {
  union {
    struct {
      UINT Swizzle  :1;
      UINT Unswizzle  :1;
      UINT AllocationIsIdle  :1;
      UINT TransferStart  :1;
      UINT TransferEnd  :1;
      UINT Reserved  :27;
    };
    UINT Value;
  };
} DXGK_TRANSFERFLAGS;
````


## -struct-fields




### -field Swizzle

[in] A UINT value that specifies whether the driver should swizzle the source to the destination during the transfer. Note that for multiple-level allocations (for example, MIP-map textures), the driver should swizzle all levels of the allocations. For more information about swizzling allocations, see <a href="https://msdn.microsoft.com/c9be52d9-36b2-4a0f-9629-01b31293af38">Locking Swizzled Allocations</a>.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Unswizzle

[in] A UINT value that specifies whether the driver should unswizzle the source to the destination during the transfer. Note that for multiple-level allocations (for example, MIP-map textures), the driver should unswizzle all levels of the allocations. For more information about swizzling allocations, see <a href="https://msdn.microsoft.com/c9be52d9-36b2-4a0f-9629-01b31293af38">Locking Swizzled Allocations</a>.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field AllocationIsIdle

[in] A UINT value that specifies whether the graphics processing unit (GPU) is using the given allocation. If this member is set, the GPU is not using the given allocation; that is, no work was queued or will be queued to the GPU until the call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> returns.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field TransferStart

[in] A UINT value that specifies whether the transfer operation is starting. If this member is set, the transfer operation is starting.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field TransferEnd

[in] A UINT value that specifies whether the transfer operation is ending. If this member is set, the transfer operation is ending.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that DXGK_TRANSFERFLAGS contains that can hold a 32-bit value that identifies the transfer-operation type.


## -remarks


You can set the transfer-operation type by setting bits in the 32-bit <b>Value</b> member or by setting individual members of the structure in the union that DXGK_TRANSFERFLAGS contains.



## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_TRANSFERFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

