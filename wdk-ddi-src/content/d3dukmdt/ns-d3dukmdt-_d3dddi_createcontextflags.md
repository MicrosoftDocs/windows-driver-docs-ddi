---
UID: NS:d3dukmdt._D3DDDI_CREATECONTEXTFLAGS
title: D3DDDI_CREATECONTEXTFLAGS (d3dukmdt.h)
description: Learn more about the D3DDDI_CREATECONTEXTFLAGS structure.
tech.root: display
ms.date: 05/21/2024
keywords: ["D3DDDI_CREATECONTEXTFLAGS structure"]
ms.keywords: D3DDDI_CREATECONTEXTFLAGS, D3DDDI_CREATECONTEXTFLAGS structure [Display Devices], D3D_other_Structs_e20f9457-1008-4c63-a924-d5fa75929be5.xml, _D3DDDI_CREATECONTEXTFLAGS, d3dukmdt/D3DDDI_CREATECONTEXTFLAGS, display.d3dddi_createcontextflags
req.header: d3dukmdt.h
req.construct-type: structure
req.include-header: D3dumddi.h, D3dkmddi.h
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
targetos: Windows
req.typenames: D3DDDI_CREATECONTEXTFLAGS
f1_keywords:
 - _D3DDDI_CREATECONTEXTFLAGS
 - d3dukmdt/_D3DDDI_CREATECONTEXTFLAGS
 - D3DDDI_CREATECONTEXTFLAGS
 - d3dukmdt/D3DDDI_CREATECONTEXTFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_CREATECONTEXTFLAGS
 - D3DDDI_CREATECONTEXTFLAGS
---

# D3DDDI_CREATECONTEXTFLAGS structure (d3dukmdt.h)



## -description

The **D3DDDI_CREATECONTEXTFLAGS** structure describes how to create a context in a call to the [**pfnCreateContextCb**](/previous-versions/ff568895(v=vs.85)) function.

## -struct-fields

### -field NullRendering

Specifies whether the GPU should process any commands that are sent by the context that is created. The **NullRendering** bit-field flag is set to inform the GPU not to process any commands that are sent by the context. The **NullRendering** bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. **NullRendering** is never set during typical operations.

### -field InitialData

When set, indicates that the context is created with initial data.

### -field DisableGpuTimeout

When set, indicates that the GPU timeout is disabled for the context.

### -field SynchronizationOnly

When set, indicates that the context is created for synchronization purposes only, and not for rendering.

### -field HwQueueSupported

When set, indicates that the context supports hardware queues, which can improve efficiency in command processing.

### -field NoKmdAccess

When set, indicates that the context is created without kernel-mode driver (KMD) access. Added in WDDM 2.3.

### -field TestContext

When set, indicates that the context is created for testing purposes. Added in WDDM 2.3.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A member in the union that is contained in D3DDDI_CREATECONTEXTFLAGS that can hold one 32-bit value that identifies how to create the context.

## -see-also

[**D3DDDICB_CREATECONTEXT**](../d3dumddi/ns-d3dumddi-_d3dddicb_createcontext.md)

[**pfnCreateContextCb**](/previous-versions/ff568895(v=vs.85))
