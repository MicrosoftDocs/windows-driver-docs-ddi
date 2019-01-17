---
UID: NS:d3dumddi._D3DDDIARG_DECODEBEGINFRAME
title: "_D3DDDIARG_DECODEBEGINFRAME"
description: The D3DDDIARG_DECODEBEGINFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should start decoding a frame.
old-location: display\d3dddiarg_decodebeginframe.htm
tech.root: display
ms.assetid: 8219beee-b27c-4f81-aef7-8d38363d4645
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DECODEBEGINFRAME, D3DDDIARG_DECODEBEGINFRAME structure [Display Devices], UMDisplayDriver_param_Structs_fdee5664-6d7b-4d54-ac34-69d216f05896.xml, _D3DDDIARG_DECODEBEGINFRAME, d3dumddi/D3DDDIARG_DECODEBEGINFRAME, display.d3dddiarg_decodebeginframe
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
-	D3DDDIARG_DECODEBEGINFRAME
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DECODEBEGINFRAME
---

# _D3DDDIARG_DECODEBEGINFRAME structure


## -description


The D3DDDIARG_DECODEBEGINFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should start decoding a frame. 


## -struct-fields




### -field hDecode

A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a> function.


### -field pPVPSetKey

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562925">DXVADDI_PVP_SETKEY</a> structure that contains a key that the driver requires for the decode device to start operating. 


## -see-also




<a href="https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff">CreateDecodeDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562925">DXVADDI_PVP_SETKEY</a>



<a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>
 

 

