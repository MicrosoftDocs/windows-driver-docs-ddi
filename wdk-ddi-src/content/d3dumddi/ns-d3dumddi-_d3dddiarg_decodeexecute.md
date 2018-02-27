---
UID: NS:d3dumddi._D3DDDIARG_DECODEEXECUTE
title: "_D3DDDIARG_DECODEEXECUTE"
author: windows-driver-content
description: The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.
old-location: display\d3dddiarg_decodeexecute.htm
old-project: display
ms.assetid: 7f5bdf39-68a7-4466-b4d9-3620b638db62
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DECODEEXECUTE
---

# _D3DDDIARG_DECODEEXECUTE structure


## -description


The D3DDDIARG_DECODEEXECUTE structure describes a Microsoft DirectX Video Acceleration (VA) decode operation to perform.


## -syntax


````
typedef struct _D3DDDIARG_DECODEEXECUTE {
  HANDLE                   hDecode;
  UINT                     NumCompBuffers;
  DXVADDI_DECODEBUFFERDESC *pCompressedBuffers;
} D3DDDIARG_DECODEEXECUTE;
````


## -struct-fields




### -field hDecode

[in] A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> function.


### -field NumCompBuffers

[in] The number of compressed buffer that are pointed to by the <b>pCompressedBuffers</b> member. 


### -field pCompressedBuffers

[in] A pointer to a list of <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a> structures that describe the compressed buffers that are passed from the host decoder to the accelerator.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DECODEEXECUTE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

