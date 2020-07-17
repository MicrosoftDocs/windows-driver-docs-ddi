---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCONTEXTCB
title: PFND3DDDI_DESTROYCONTEXTCB (d3dumddi.h)
description: The pfnDestroyContextCb function destroys the context that was created through a call to the pfnCreateContextCb function.
old-location: display\pfndestroycontextcb.htm
tech.root: display
ms.assetid: 6b65d75b-544b-4153-b821-d59d6f85673d
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DESTROYCONTEXTCB callback function"]
ms.keywords: D3Druntime_Functions_61661c25-9c5c-4ca1-8015-a32ed840fd0a.xml, PFND3DDDI_DESTROYCONTEXTCB, PFND3DDDI_DESTROYCONTEXTCB callback, d3dumddi/pfnDestroyContextCb, display.pfndestroycontextcb, pfnDestroyContextCb, pfnDestroyContextCb callback function [Display Devices]
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
 - "d3dumddi/pfnDestroyContextCb"
 - "pfnDestroyContextCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnDestroyContextCb
product:
 - Windows
---

# PFND3DDDI_DESTROYCONTEXTCB callback function

## -description

The <b>pfnDestroyContextCb</b> function destroys the context that was created through a call to the <a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function.

## -parameters

### -param hDevice

A handle to a display device (that is, the graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroycontext">D3DDDICB_DESTROYCONTEXT</a> structure that contains a handle to the context to destroy.

## -returns

<b>pfnDestroyContextCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The context was successfully destroyed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
 

This function might also return other HRESULT values.

## -remarks

If the specified context has not finished the work that is currently queued to it, the <b>pfnDestroyContextCb</b> function blocks until the context finishes its work and then returns. 

<b>pfnDestroyContextCb</b> returns an error if the context to destroy currently owns a synchronization object.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnDestroyContextCb</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/changes-from-direct3d-10">Changes from Direct3D 10</a>.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroycontext">D3DDDICB_DESTROYCONTEXT</a>



<a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a>

