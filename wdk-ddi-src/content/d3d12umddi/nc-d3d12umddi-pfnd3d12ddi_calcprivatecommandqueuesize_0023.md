---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
author: windows-driver-content
description: The pfnCalcPrivateCommandQueueSize callback function is used to calculate the size of a private command queue.
old-location: display\pfnd3d12ddi_calcprivatecommandqueuesize_0023.htm
ms.assetid: 70A81285-97CD-4526-8EB0-F00908B2D331
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023, PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback, d3d12umddi/pfnCalcPrivateCommandQueueSize, display.pfnd3d12ddi_calcprivatecommandqueuesize_0023, pfnCalcPrivateCommandQueueSize, pfnCalcPrivateCommandQueueSize callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnCalcPrivateCommandQueueSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback function


## -description


The <i>pfnCalcPrivateCommandQueueSize</i> callback function is used to calculate the size of a private command queue.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param *








#### - CreateCommandQueue [in]

An argument used to create a command queue.


#### - hDevice

The handle of a device.


## -returns



The size of the queue.




## -remarks



Access this callback function by using a device functions core structure, such as the <b>D3D12DDI_DEVICE_FUNCS_CORE_0003</b> structure.



