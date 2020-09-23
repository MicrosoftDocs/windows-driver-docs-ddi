---
UID: NS:d3dumddi._D3DDDIARG_GETPITCH
title: _D3DDDIARG_GETPITCH (d3dumddi.h)
description: The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the GetPitch function retrieves the pitch.
old-location: display\d3dddiarg_getpitch.htm
tech.root: display
ms.assetid: 59661cfe-4a1f-4805-9421-7f694e82f8d2
ms.date: 05/10/2018
keywords: ["D3DDDIARG_GETPITCH structure"]
ms.keywords: D3DDDIARG_GETPITCH, D3DDDIARG_GETPITCH structure [Display Devices], UMDisplayDriver_param_Structs_02e95329-8eba-41a3-ae4e-d8830b47ada6.xml, _D3DDDIARG_GETPITCH, d3dumddi/D3DDDIARG_GETPITCH, display.d3dddiarg_getpitch
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_GETPITCH is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_GETPITCH
f1_keywords:
 - _D3DDDIARG_GETPITCH
 - d3dumddi/_D3DDDIARG_GETPITCH
 - D3DDDIARG_GETPITCH
 - d3dumddi/D3DDDIARG_GETPITCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_GETPITCH
---

# _D3DDDIARG_GETPITCH structure


## -description

The D3DDDIARG_GETPITCH structure describes an encrypted surface for which the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getpitch">GetPitch</a> function retrieves the pitch.

## -struct-fields

### -field hCryptoSession

[in] A handle to the encryption session.

### -field hResource

[in] A handle to the resource.

### -field SubResourceIndex

[in] The zero-based index into the resource, which the <b>hResource</b> handle specifies. This index indicates the encrypted surface.

### -field Pitch

[out] The pitch, in bytes, of the encrypted surface. The user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getpitch">GetPitch</a> function returns this pitch value to the Direct3D runtime.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getpitch">GetPitch</a>