---
UID: NS:d3dumddi._D3DDDIARG_DECODEEXECUTE
title: "_D3DDDIARG_DECODEEXECUTE"
author: windows-driver-content
description: The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.
old-location: display\d3dddiarg_decodeexecute.htm
tech.root: display
ms.assetid: 7f5bdf39-68a7-4466-b4d9-3620b638db62
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_DECODEEXECUTE, D3DDDIARG_DECODEEXECUTE structure [Display Devices], UMDisplayDriver_param_Structs_bd4aee7e-91f5-41dc-bb63-0fed88e04c7d.xml, _D3DDDIARG_DECODEEXECUTE, d3dumddi/D3DDDIARG_DECODEEXECUTE, display.d3dddiarg_decodeexecute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_DECODEEXECUTE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DECODEEXECUTE
---

# _D3DDDIARG_DECODEEXECUTE structure


## -description


The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.


## -struct-fields




### -field hDecode

[in] A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a> function.


### -field NumCompBuffers

[in] The number of compressed buffer that are pointed to by the <b>pCompressedBuffers</b> member. 


### -field pCompressedBuffers

[in] A pointer to a list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562896">DXVADDI_DECODEBUFFERDESC</a> structures that describe the compressed buffers that are passed from the host decoder to the accelerator.


## -see-also




<a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562896">DXVADDI_DECODEBUFFERDESC</a>



<a href="https://msdn.microsoft.com/e12496c0-e3e4-437e-9f84-a30ee99b4541">DecodeExecute</a>
 

 

