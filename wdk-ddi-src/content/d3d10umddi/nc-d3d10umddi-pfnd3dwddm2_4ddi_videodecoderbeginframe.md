---
UID: NC:d3d10umddi.PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME
title: PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME (d3d10umddi.h)
description: Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.
ms.assetid: 760c83f0-a3d7-4e6f-bce4-041ecfd4f667
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME callback function

## -description

Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.

## -prototype

```cpp
//Declaration

PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME Pfnd3dwddm24DdiVideodecoderbeginframe;

// Definition

HRESULT Pfnd3dwddm24DdiVideodecoderbeginframe
(
	D3D10DDI_HDEVICE hDevice
	D3D11_1DDI_HDECODE hDecode
	CONST D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME *pBeginFrame
)
{...}

PFND3DWDDM2_4DDI_VIDEODECODERBEGINFRAME


```

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hDecode

A handle to the video decoder object that was created through a call to the CreateVideoDecoder function.

### -param *pBeginFrame

A pointer to a D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0 structure. For more information, see the Remarks section.

## -returns

Returns one of the following HRESULT values:

| Return code | Description |
|---|---|
|S_OK|The session key for the cryptographic session was negotiated successfully.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

If this function returns S_OK, the Microsoft Direct3D runtime calls the VideoDecoderSubmitBuffers function to perform the decoding operations. When all decoding operations have been executed, the runtime calls the VideoDecoderEndFrame function to stop the decoding operation on a video frame.

> [!NOTE]
> Each call to VideoDecoderBeginFrame must have a matching call to VideoDecoderEndFrame, and VideoDecoderBeginFrame calls cannot be nested.

The [D3DWDDM2_4DDIARG_VIDEODECODERBEGINFRAME_RS4_0](ns-d3d10umddi-d3dwddm2_4ddiarg_videodecoderbeginframe_rs4_0.md) structure contains the following data:

* The resource that will receive the decrypted and decoded data.
* A content key that was used to encrypt the video frame data.

If the *pContentKey* member of this structure is not set to NULL, the buffer that is referenced by this member contains a per-frame content key. This key must be used to decrypt the data instead of using the session key.

> [!NOTE]
> If the *pContentKey* member is not set to NULL, the buffer that is referenced by this member is encrypted by using the session key with the AES-ECB algorithm.

If the pContentKey member is set to NULL, the video frame data should be decrypted by using the session key.


## -see-also

[CreateVideoDecoder](nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md)
[NegotiateCryptoSessionKeyeExchange](nc-d3d10umddi-pfnd3dwddm2_4ddi_negotiatecryptosessionkeyexchange.md)
