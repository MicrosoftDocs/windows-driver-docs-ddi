---
UID: NC:d3d12umddi.PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062
title: PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062
description: PfnQueueProcessingWorkCb is provided by the runtime and called by user mode drivers to register and queue work items.
tech.root: display
ms.date: 04/04/2019
keywords: ["PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
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
ms.custom: D3D12 Release 6, Build rev 2., 19H1
f1_keywords:
 - PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062
 - d3d12umddi/PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062 callback function


## -description

*PfnQueueProcessingWorkCb* is provided by the runtime and called by user mode drivers to register and queue work items. 

The runtime is responsible for managing threads, either directly, or through a Thread Pool. The UMD will not have any control over which thread the work is processed on. Work will be processed in the order it was received. *PfnQueueProcessingWorkCb* may be called from multiple threads concurrently and is thread safe (runtime will serialize).

## -parameters

### -param hRTDevice

[in] The handle of the device for the driver to use when it calls back into the runtime.

### -param pfnCallback

[in] Pointer to a [PFND3D12DDI_UMD_CALLBACK_METHOD](nc-d3d12umddi-pfnd3d12ddi_umd_callback_method.md) callback that is called from the thread where work is being performed.

### -param pfnCancel

[in, opt] Pointer to a [PFND3D12DDI_UMD_CALLBACK_METHOD](nc-d3d12umddi-pfnd3d12ddi_umd_callback_method.md) callback that is called if the device is destroyed before *pfnCallback* has executed.

### -param pContext

[in, opt] Pointer to a device context that is passed to *pfnCallback* or *pfnCancel*.

## -returns

Returns HRESULT.

## -prototype

```
//Declaration

PFND3D12DDI_QUEUEPROCESSINGWORK_CB_0062 Pfnd3d12ddiQueueprocessingworkCb0062; 

// Definition

HRESULT Pfnd3d12ddiQueueprocessingworkCb0062 
(
	D3D12DDI_HRTDEVICE hRTDevice
	PFND3D12DDI_UMD_CALLBACK_METHOD pfnCallback
	PFND3D12DDI_UMD_CALLBACK_METHOD pfnCancel
	 void *pContext
)
{...}

```

## -remarks

## -see-also

