---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023
author: windows-driver-content
description: The pfnCalcPrivateCommandQueueSize callback function is used to calculate the size of a private command queue.
old-location: display\pfnd3d12ddi_calcprivatecommandqueuesize_0023.htm
old-project: display
ms.assetid: 70A81285-97CD-4526-8EB0-F00908B2D331
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_calcprivatecommandqueuesize_0023, pfnCalcPrivateCommandQueueSize callback function [Display Devices], pfnCalcPrivateCommandQueueSize, PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023, PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023, d3d12umddi/pfnCalcPrivateCommandQueueSize
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnCalcPrivateCommandQueueSize
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 callback


## -description


The <i>pfnCalcPrivateCommandQueueSize</i> callback function is used to calculate the size of a private command queue. 


## -prototype


````
PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0023 pfnCalcPrivateCommandQueueSize;

SIZE_T APIENTRY* pfnCalcPrivateCommandQueueSize(
             D3D12DDI_HDEVICE                    hDevice,
  _In_ const D3D12DDIARG_CREATECOMMANDQUEUE_0023 *CreateCommandQueue
)
{ ... }
````


## -parameters




### -param D3D12DDI_HDEVICE


### -param *








#### - CreateCommandQueue [in]

An argument used to create a command queue. 


#### - hDevice

The handle of a device.


## -returns



The size of the queue.




## -remarks



Access this callback function by using a device functions core structure, such as the <b>D3D12DDI_DEVICE_FUNCS_CORE_0003</b> structure.



