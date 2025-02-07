---
UID: NS:d3dkmddi._DXGKARG_ESCAPE
title: DXGKARG_ESCAPE (d3dkmddi.h)
description: The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: DXGKARG_ESCAPE
f1_keywords:
 - _DXGKARG_ESCAPE
 - d3dkmddi/_DXGKARG_ESCAPE
 - DXGKARG_ESCAPE
 - d3dkmddi/DXGKARG_ESCAPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_ESCAPE
 - DXGKARG_ESCAPE
---

# DXGKARG_ESCAPE structure

## -description

The **DXGKARG_ESCAPE** structure describes information that the user-mode display driver (UMD) shares with the display miniport driver (KMD).

## -struct-fields

### -field hDevice [in]

A handle to the display device (graphics context) that was originally passed to KMD's [**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md) function.

### -field Flags [in]

A [**D3DDDI_ESCAPEFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_escapeflags.md) structure that indicates, in bit-field flags, how to share information.

### -field pPrivateDriverData [in/out]

A pointer to a buffer that contains the information that the display miniport driver and the user-mode display driver share.

### -field PrivateDriverDataSize [in/out]

The size, in bytes, of the buffer that **pPrivateDriverData** points to.

### -field hContext [in]

A handle to the context that was originally passed to KMD's [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md) function.

### -field hKmdProcessHandle [in]

A driver handle that is returned by the KMD from the call to [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md). The driver must check the handle for NULL. The handle is created when the first DXG device is created for a process. The handle is destroyed when the last adapter handle is closed for a process.

## -see-also

[**D3DDDI_ESCAPEFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_escapeflags.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)

[**DxgkDdiCreateDevice**](nc-d3dkmddi-dxgkddi_createdevice.md)

[**DxgkDdiEscape**](nc-d3dkmddi-dxgkddi_escape.md)
