---
UID: NS:d3dumddi._DXVADDI_PRIVATEDATA
title: DXVADDI_PRIVATEDATA (d3dumddi.h)
description: Learn more about the DXVADDI_PRIVATEDATA structure.
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
req.typenames: DXVADDI_PRIVATEDATA
f1_keywords:
 - _DXVADDI_PRIVATEDATA
 - d3dumddi/_DXVADDI_PRIVATEDATA
 - DXVADDI_PRIVATEDATA
 - d3dumddi/DXVADDI_PRIVATEDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _DXVADDI_PRIVATEDATA
 - DXVADDI_PRIVATEDATA
---

# DXVADDI_PRIVATEDATA structure

## -description

The **DXVADDI_PRIVATEDATA** structure encapsulates private data for a DirectX Video Acceleration (DXVA) extension device.

## -struct-fields

### -field pData [in]

A pointer to a buffer that contains private, driver-defined data for the extension device.

### -field DataSize [in]

The size, in bytes, of the buffer that is pointed to by **pData**.

## -remarks

For more information, see [Extended Support for DirectX VA 2.0](/windows-hardware/drivers/display/extended-support-for-directx-va-2-0).

## -see-also

[**CreateExtensionDevice**](nc-d3dumddi-pfnd3dddi_createextensiondevice.md)

[**D3DDDIARG_CREATEEXTENSIONDEVICE**](ns-d3dumddi-_d3dddiarg_createextensiondevice.md)

[**DecodeExtensionExecute**](nc-d3dumddi-pfnd3dddi_decodeextensionexecute.md)

[**D3DDDIARG_DECODEEXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_decodeextensionexecute.md)

[**ExtensionExecute**](nc-d3dumddi-pfnd3dddi_extensionexecute.md)

[**D3DDDIARG_EXTENSIONEXECUTE**](ns-d3dumddi-_d3dddiarg_extensionexecute.md)
