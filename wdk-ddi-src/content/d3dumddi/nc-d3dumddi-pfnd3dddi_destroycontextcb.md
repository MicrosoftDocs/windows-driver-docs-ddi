---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCONTEXTCB
title: PFND3DDDI_DESTROYCONTEXTCB (d3dumddi.h)
description: Learn more about the PFND3DDDI_DESTROYCONTEXTCB callback function.
tech.root: display
ms.date: 12/19/2024
keywords: ["PFND3DDDI_DESTROYCONTEXTCB callback function"]
ms.keywords: D3Druntime_Functions_61661c25-9c5c-4ca1-8015-a32ed840fd0a.xml, PFND3DDDI_DESTROYCONTEXTCB, PFND3DDDI_DESTROYCONTEXTCB callback, d3dumddi/pfnDestroyContextCb, display.pfndestroycontextcb, pfnDestroyContextCb, pfnDestroyContextCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_DESTROYCONTEXTCB
 - d3dumddi/PFND3DDDI_DESTROYCONTEXTCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DESTROYCONTEXTCB
---

# PFND3DDDI_DESTROYCONTEXTCB callback function

## -description

The D3D runtime's **pfnDestroyContextCb** function destroys a context that was created through a call to its [**pfnCreateContextCb**](nc-d3dumddi-pfnd3dddi_createcontextcb.md) function.

## -parameters

### -param hDevice

[in] Handle to a display device (that is, the graphics context).

### -param unnamedParam2

[in] Pointer to a [**D3DDDICB_DESTROYCONTEXT**](ns-d3dumddi-_d3dddicb_destroycontext.md) structure that identifies the context to destroy.

## -returns

**pfnDestroyContextCb** returns an HRESULT to indicate the success or failure of the context deletion request. Common return values include:

|Return code|Description|
|--- |--- |
|S_OK|The context was successfully destroyed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

## -remarks

If the specified context has not finished the work that is currently queued to it, the **pfnDestroyContextCb** function blocks until the context finishes its work and then returns.

**pfnDestroyContextCb** returns an error if the context to destroy currently owns a synchronization object.

For information about how the driver calls **pfnDestroyContextCb** starting in Direct3D version 11, see [Changes from Direct3D 10](/windows-hardware/drivers/display/changes-from-direct3d-10).

The following code example shows how to destroy the default context for a display device.

```cpp
    if (m_d3dCallbacks.pfnDestroyContextCb) {
        D3DDDICB_DESTROYCONTEXT DestroyContext;
        DestroyContext.hContext = m_sContexts[MULTI_ENGINE_NODE_3D].hContext;
        m_d3dCallbacks.pfnDestroyContextCb(m_hD3D, &DestroyContext);
        m_sContexts[MULTI_ENGINE_NODE_3D].hContext = NULL;
    }
```

## -see-also

[**D3DDDICB_DESTROYCONTEXT**](ns-d3dumddi-_d3dddicb_destroycontext.md)

[**pfnCreateContextCb**](nc-d3dumddi-pfnd3dddi_createcontextcb.md)