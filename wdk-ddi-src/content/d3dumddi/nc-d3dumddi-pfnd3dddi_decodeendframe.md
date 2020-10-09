---
UID: NC:d3dumddi.PFND3DDDI_DECODEENDFRAME
title: PFND3DDDI_DECODEENDFRAME (d3dumddi.h)
description: The DecodeEndFrame function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.
old-location: display\decodeendframe.htm
tech.root: display
ms.assetid: 6e8d3280-6ddc-4593-9208-c4f0c9ff254c
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DECODEENDFRAME callback function"]
ms.keywords: DecodeEndFrame, DecodeEndFrame callback function [Display Devices], PFND3DDDI_DECODEENDFRAME, PFND3DDDI_DECODEENDFRAME callback, UserModeDisplayDriver_Functions_c80e307b-2b64-4b43-84c3-cae711e8282f.xml, d3dumddi/DecodeEndFrame, display.decodeendframe
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_DECODEENDFRAME
 - d3dumddi/PFND3DDDI_DECODEENDFRAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DecodeEndFrame
product:
 - Windows
---

# PFND3DDDI_DECODEENDFRAME callback function


## -description

The <b>DecodeEndFrame</b> function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodeendframe">D3DDDIARG_DECODEENDFRAME</a> structure that describes the DirectX VA decoder that should stop decoding a frame.

## -returns

<b>DecodeEndFrame</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Decoding successfully completed.|
|E_OUTOFMEMORY|DecodeEndFrame could not allocate the required memory for it to complete.|

## -remarks

The <b>DecodeEndFrame</b> function notifies the user-mode display driver that its <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeexecute">DecodeExecute</a> function can no longer be called on the specified decode device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decodeendframe">D3DDDIARG_DECODEENDFRAME</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decodeexecute">DecodeExecute</a>