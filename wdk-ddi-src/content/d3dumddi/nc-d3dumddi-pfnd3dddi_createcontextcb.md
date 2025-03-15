---
UID: NC:d3dumddi.PFND3DDDI_CREATECONTEXTCB
title: PFND3DDDI_CREATECONTEXTCB (d3dumddi.h)
description: Learn more about the PFND3DDDI_CREATECONTEXTCB callback function.
ms.date: 12/19/2024
keywords: ["PFND3DDDI_CREATECONTEXTCB callback function"]
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DDDI_CREATECONTEXTCB
 - d3dumddi/PFND3DDDI_CREATECONTEXTCB
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_CREATECONTEXTCB
dev_langs:
 - c++
---

# PFND3DDDI_CREATECONTEXTCB callback function

## -description

The Direct3D runtime's **pfnCreateContextCb** callback function creates a context.

## -parameters

### -param hDevice

[in]  Handle to the device for which the context is to be created.

### -param unnamedParam2

[in/out] Pointer to a [**D3DDDICB_CREATECONTEXT**](ns-d3dumddi-_d3dddicb_createcontext.md) structure that the driver fills with the necessary information for creating the context. This structure includes details such as node ordinal, engine affinity, and flags that specify the behavior and capabilities of the context to be created. Upon successful completion, the runtime updates this structure with information about the newly created context.

## -returns

**pfnCreateContextCb** returns an HRESULT to indicate the success or failure of the context creation request. Common return values include:

| Return code | Meaning |
| ----------- | ------- |
| S_OK          |  The context was successfully created. |
| E_OUTOFMEMORY | There is insufficient memory to create the context. |
| E_INVALIDARG  | One or more of the provided arguments are invalid. |

## -remarks

The user-mode display driver (UMD) must explicitly call **pfnCreateContextCb** from its [**CreateDevice**](nc-d3dumddi-pfnd3dddi_createdevice.md) implementation to create a GPU context associated with the device. GPU contexts are GPU threads of execution on a newly created device.

The context encapsulates state and command buffers that the GPU uses to perform rendering operations. UMD is responsible for managing the lifecycle of contexts it creates, including their eventual destruction to free up resources.

For more information about the creation of a rendering device, see [Windows Display Driver Model (WDDM) operation flow](/windows-hardware/drivers/display/windows-vista-and-later-display-driver-model-operation-flow).

## -see-also

[**D3DDDICB_CREATECONTEXT**](ns-d3dumddi-_d3dddicb_createcontext.md)

[**pfnDestroyContextCb**](nc-d3dumddi-pfnd3dddi_destroycontextcb.md)
