---
UID: NS:d3dumddi._D3DDDIARG_CREATEDECODEDEVICE
title: D3DDDIARG_CREATEDECODEDEVICE (d3dumddi.h)
description: Learn more about the D3DDDIARG_CREATEDECODEDEVICE structure.
tech.root: display
ms.date: 09/10/2024
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DDDIARG_CREATEDECODEDEVICE
f1_keywords:
 - _D3DDDIARG_CREATEDECODEDEVICE
 - d3dumddi/_D3DDDIARG_CREATEDECODEDEVICE
 - D3DDDIARG_CREATEDECODEDEVICE
 - d3dumddi/D3DDDIARG_CREATEDECODEDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_CREATEDECODEDEVICE
 - D3DDDIARG_CREATEDECODEDEVICE
---

# D3DDDIARG_CREATEDECODEDEVICE structure

## -description

The **D3DDDIARG_CREATEDECODEDEVICE** structure describes a DirectX Video Acceleration (DXVA) decode device to create.

## -struct-fields

### -field pGuid [in]

A pointer to the GUID that represents the DXVA decode type. The Direct3D runtime calls the [**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md) function to query for the supported GUIDs.

### -field VideoDesc [in]

The [**DXVADDI_VIDEODESC**](ns-d3dumddi-_dxvaddi_videodesc.md) structure for the video stream that the decode device should decode.

### -field pConfig [in]

A pointer to the [**DXVADDI_CONFIGPICTUREDECODE**](ns-d3dumddi-_dxvaddi_configpicturedecode.md) structure that contains the DirectX VA connection configuration data for compressed picture decoding that the decode device requires. The Direct3D runtime calls the [**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md) function to query for the supported configurations.

### -field hDecode [in/out]

A handle to the decode device. The user-mode display driver generates this handle for the Direct3D runtime to use to identify the decode device in subsequent calls.

## -see-also

[**CreateDecodeDevice**](nc-d3dumddi-pfnd3dddi_createdecodedevice.md)  
  
[**DXVADDI_CONFIGPICTUREDECODE**](ns-d3dumddi-_dxvaddi_configpicturedecode.md)  
  
[**DXVADDI_VIDEODESC**](ns-d3dumddi-_dxvaddi_videodesc.md)  
  
[**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md)
