---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDQUEUE_0023
title: PFND3D12DDI_CREATECOMMANDQUEUE_0023 (d3d12umddi.h)
description: The pfnCreateCommandQueue callback function is used to create command queue.
old-location: display\pfnd3d12ddi_createcommandqueue_0023.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CREATECOMMANDQUEUE_0023 callback function"]
ms.keywords: PFND3D12DDI_CREATECOMMANDQUEUE_0023, PFND3D12DDI_CREATECOMMANDQUEUE_0023 callback, d3d12umddi/pfnCreateCommandQueue, display.pfnd3d12ddi_createcommandqueue_0023, pfnCreateCommandQueue, pfnCreateCommandQueue callback function [Display Devices]
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_CREATECOMMANDQUEUE_0023
 - d3d12umddi/PFND3D12DDI_CREATECOMMANDQUEUE_0023
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_CREATECOMMANDQUEUE_0023
---

# PFND3D12DDI_CREATECOMMANDQUEUE_0023 callback function


## -description

The <i>pfnCreateCommandQueue</i> callback function is used to create command queue.

## -parameters

### -param unnamedParam1

The handle of a device.

### -param unnamedParam2

An argument used to create a command queue.

### -param unnamedParam3

The handle of the command queue for the driver to use when it calls back into the runtime.

### -param unnamedParam4

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

Access this callback function by using a device functions core structure, such as the <b>D3D12DDI_DEVICE_FUNCS_CORE_0003</b> structure.

