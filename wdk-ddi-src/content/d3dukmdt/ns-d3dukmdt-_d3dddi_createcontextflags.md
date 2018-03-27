---
UID: NS:d3dukmdt._D3DDDI_CREATECONTEXTFLAGS
title: "_D3DDDI_CREATECONTEXTFLAGS"
author: windows-driver-content
description: The D3DDDI_CREATECONTEXTFLAGS structure describes how to create a context in a call to the pfnCreateContextCb function.
old-location: display\d3dddi_createcontextflags.htm
old-project: display
ms.assetid: e450f85c-4c73-44a8-9d0a-da2c212c87c9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_CREATECONTEXTFLAGS, D3DDDI_CREATECONTEXTFLAGS structure [Display Devices], D3D_other_Structs_e20f9457-1008-4c63-a924-d5fa75929be5.xml, _D3DDDI_CREATECONTEXTFLAGS, d3dukmdt/D3DDDI_CREATECONTEXTFLAGS, display.d3dddi_createcontextflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_CREATECONTEXTFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_CREATECONTEXTFLAGS
---

# _D3DDDI_CREATECONTEXTFLAGS structure


## -description


The D3DDDI_CREATECONTEXTFLAGS structure describes how to create a context in a call to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.


## -struct-fields




### -field NullRendering

A UINT value that specifies whether the graphics processing unit (GPU) should process any commands that are sent by the context that is created. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands that are sent by the context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field InitialData

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field DisableGpuTimeout

 


### -field SynchronizationOnly

 


### -field HwQueueSupported

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFD) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_CREATECONTEXTFLAGS that can hold one 32-bit value that identifies how to create the context.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544143">D3DDDICB_CREATECONTEXT</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_CREATECONTEXTFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

