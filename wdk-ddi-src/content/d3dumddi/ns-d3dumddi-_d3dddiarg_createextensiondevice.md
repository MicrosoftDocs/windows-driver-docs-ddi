---
UID: NS:d3dumddi._D3DDDIARG_CREATEEXTENSIONDEVICE
title: D3DDDIARG_CREATEEXTENSIONDEVICE (d3dumddi.h)
description: Learn more about the D3DDDIARG_CREATEEXTENSIONDEVICE structure.
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
req.typenames: D3DDDIARG_CREATEEXTENSIONDEVICE
f1_keywords:
 - _D3DDDIARG_CREATEEXTENSIONDEVICE
 - d3dumddi/_D3DDDIARG_CREATEEXTENSIONDEVICE
 - D3DDDIARG_CREATEEXTENSIONDEVICE
 - d3dumddi/D3DDDIARG_CREATEEXTENSIONDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_CREATEEXTENSIONDEVICE
 - D3DDDIARG_CREATEEXTENSIONDEVICE
---

# D3DDDIARG_CREATEEXTENSIONDEVICE structure

## -description

The **D3DDDIARG_CREATEEXTENSIONDEVICE** structure describes a DirectX Video Acceleration (DirectX VA) extension device to create.

## -struct-fields

### -field pGuid [in]

A pointer to the GUID that represents the DirectX VA extension type. The Direct3D runtime calls the [**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md)</a> function to query for the supported extension GUIDs.

### -field pPrivate [in]

A pointer to the [**DXVADDI_PRIVATEDATA**](ns-d3dumddi-_dxvaddi_privatedata.md) structure that contains data needed by the driver to create the extension device.

### -field hExtension [out]

A handle to the extension device. The user-mode driver creates this handle. The Direct3D runtime uses it to identify the extension device in subsequent calls.

## -remarks

For more information, see [Creating and Using a DirectX VA 2.0 Extension Device](/windows-hardware/drivers/display/creating-and-using-a-directx-va-2-0-extension-device).

## -see-also

[**CreateExtensionDevice**](nc-d3dumddi-pfnd3dddi_createextensiondevice.md)

[**DXVADDI_PRIVATEDATA**](ns-d3dumddi-_dxvaddi_privatedata.md)

[**GetCaps**](nc-d3dumddi-pfnd3dddi_getcaps.md)
