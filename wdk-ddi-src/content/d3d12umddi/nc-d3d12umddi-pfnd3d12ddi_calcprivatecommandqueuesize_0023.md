---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 (d3d12umddi.h)
description: The PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback function calculates the size of a private command queue.
old-location: display\pfnd3d12ddi_calcprivatecommandqueuesize_0023.htm
ms.date: 05/24/2022
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

The **PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023** callback function is used to calculate the size of a private command queue.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

The CreateCommandQueue argument is used to create a command queue.

## -returns

The size of the queue.

## -remarks

Access this callback function by using a device functions core structure, such as the **D3D12DDI_DEVICE_FUNCS_CORE_0003** structure.
