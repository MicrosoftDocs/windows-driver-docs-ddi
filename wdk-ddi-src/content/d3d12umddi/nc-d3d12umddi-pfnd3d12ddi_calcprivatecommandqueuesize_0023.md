---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 (d3d12umddi.h)
description: The pfnCalcPrivateCommandQueueSize callback function is used to calculate the size of a private command queue.
old-location: display\pfnd3d12ddi_calcprivatecommandqueuesize_0023.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023, PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback, d3d12umddi/pfnCalcPrivateCommandQueueSize, display.pfnd3d12ddi_calcprivatecommandqueuesize_0023, pfnCalcPrivateCommandQueueSize, pfnCalcPrivateCommandQueueSize callback function [Display Devices]
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
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
 - d3d12umddi/PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
---

# PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback function


## -description

The <i>pfnCalcPrivateCommandQueueSize</i> callback function is used to calculate the size of a private command queue.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

The CreateCommandQueue argument is used to create a command queue.

### -param CreateCommandQueue 

[in]
An argument used to create a command queue.

### -param hDevice

The handle of a device.

## -returns

The size of the queue.

## -remarks

Access this callback function by using a device functions core structure, such as the <b>D3D12DDI_DEVICE_FUNCS_CORE_0003</b> structure.

