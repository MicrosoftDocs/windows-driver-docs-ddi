---
UID: NS:d3dumddi._D3DDDIARG_DECODEEXTENSIONEXECUTE
title: "_D3DDDIARG_DECODEEXTENSIONEXECUTE"
author: windows-driver-content
description: The D3DDDIARG_DECODEEXTENSIONEXECUTE structure describes a nonstandard Microsoft DirectX Video Acceleration (VA) decode operation to perform.
old-location: display\d3dddiarg_decodeextensionexecute.htm
old-project: display
ms.assetid: 10c69928-a12f-4583-a3cc-7c4a81da4b03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_DECODEEXTENSIONEXECUTE, D3DDDIARG_DECODEEXTENSIONEXECUTE structure [Display Devices], UMDisplayDriver_param_Structs_f1b48d7e-6774-465e-99fd-29aaaf0726e1.xml, _D3DDDIARG_DECODEEXTENSIONEXECUTE, d3dumddi/D3DDDIARG_DECODEEXTENSIONEXECUTE, display.d3dddiarg_decodeextensionexecute
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
-	D3DDDIARG_DECODEEXTENSIONEXECUTE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DECODEEXTENSIONEXECUTE
---

# _D3DDDIARG_DECODEEXTENSIONEXECUTE structure


## -description


The D3DDDIARG_DECODEEXTENSIONEXECUTE structure describes a nonstandard Microsoft DirectX Video Acceleration (VA) decode operation to perform.


## -syntax


````
typedef struct _D3DDDIARG_DECODEEXTENSIONEXECUTE {
  HANDLE                hDecode;
  UINT                  Function;
  DXVADDI_PRIVATEDATA   *pPrivateInput;
  DXVADDI_PRIVATEDATA   *pPrivateOutput;
  UINT                  NumBuffers;
  DXVADDI_PRIVATEBUFFER *pBuffers;
} D3DDDIARG_DECODEEXTENSIONEXECUTE;
````


## -struct-fields




### -field hDecode

[in] A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> function.


### -field Function

[in] A specific decode operation to perform. The possible values for this member are defined by the nonstandard decode device.


### -field pPrivateInput

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to perform the decode operation.


### -field pPrivateOutput

[out] A pointer to a DXVADDI_PRIVATEDATA structure that contains data about the decode operation that the driver returns.


### -field NumBuffers

[in] The number of buffers in the list that is pointed to by <b>pBuffers</b>.


### -field pBuffers


      [in] A pointer to a list of <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatebuffer.md">DXVADDI_PRIVATEBUFFER</a> structures that describe private buffers that a nonstandard decoder uses to perform a decode operation.
     


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatedata.md">DXVADDI_PRIVATEDATA</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeextensionexecute.md">DecodeExtensionExecute</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_privatebuffer.md">DXVADDI_PRIVATEBUFFER</a>



 

 


