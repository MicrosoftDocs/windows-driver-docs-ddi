---
UID: NS:d3dkmthk._D3DKMT_CREATECONTEXTVIRTUAL
title: D3DKMT_CREATECONTEXTVIRTUAL (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATECONTEXTVIRTUAL structure.
old-location: display\d3dkmt_createcontextvirtual.htm
ms.date: 02/28/2023
keywords: ["D3DKMT_CREATECONTEXTVIRTUAL structure"]
ms.keywords: D3DKMT_CREATECONTEXTVIRTUAL, D3DKMT_CREATECONTEXTVIRTUAL structure [Display Devices], _D3DKMT_CREATECONTEXTVIRTUAL, d3dkmthk/D3DKMT_CREATECONTEXTVIRTUAL, display.d3dkmt_createcontextvirtual
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: D3DKMT_CREATECONTEXTVIRTUAL
f1_keywords:
 - _D3DKMT_CREATECONTEXTVIRTUAL
 - d3dkmthk/_D3DKMT_CREATECONTEXTVIRTUAL
 - D3DKMT_CREATECONTEXTVIRTUAL
 - d3dkmthk/D3DKMT_CREATECONTEXTVIRTUAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATECONTEXTVIRTUAL
 - D3DKMT_CREATECONTEXTVIRTUAL
---

# D3DKMT_CREATECONTEXTVIRTUAL structure

## -description

**D3DKMT_CREATECONTEXTVIRTUAL** is used with [**D3DKMTCreateContextVirtual**](nf-d3dkmthk-d3dkmtcreatecontextvirtual.md) to create a kernel-mode device context that supports virtual addressing.

## -struct-fields

### -field hDevice

[in] A handle to the device that owns the context being created.

### -field NodeOrdinal

[in] The zero-based index for the node that the context is scheduled on.

### -field EngineAffinity

[in] The zero-based index for the engine, within the node that **NodeOrdinal** specifies, that the context can run in.

### -field Flags

[in] A [**D3DDDI_CREATECONTEXTFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags.md) structure that indicates, in bit-field flags, how to create the context.

### -field pPrivateDriverData

[in] A pointer to private data that is passed to a display miniport driver.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the private data that **pPrivateDriverData** points to.

### -field ClientHint

[in] A hint describing which graphics subsystem is creating the context.

### -field hContext

[out] A handle to the created device context.

## -see-also

[**D3DDDI_CREATECONTEXTFLAGS**](../d3dukmdt/ns-d3dukmdt-_d3dddi_createcontextflags.md)

[**D3DKMTCreateContextVirtual**](nf-d3dkmthk-d3dkmtcreatecontextvirtual.md)
