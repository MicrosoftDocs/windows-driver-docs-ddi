---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECOMMANDQUEUE_0023
title: PFND3D12DDI_CREATECOMMANDQUEUE_0023
author: windows-driver-content
description: The pfnCreateCommandQueue callback function is used to create command queue.
old-location: display\pfnd3d12ddi_createcommandqueue_0023.htm
old-project: display
ms.assetid: 1DA52354-2338-4214-8489-B6BFCD6060FB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D12DDI_CREATECOMMANDQUEUE_0023, d3d12umddi/pfnCreateCommandQueue, display.pfnd3d12ddi_createcommandqueue_0023, pfnCreateCommandQueue, pfnCreateCommandQueue callback function [Display Devices]
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
-	pfnCreateCommandQueue
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATECOMMANDQUEUE_0023 callback


## -description


The <i>pfnCreateCommandQueue</i> callback function is used to create command queue. 


## -prototype


````
PFND3D12DDI_CREATECOMMANDQUEUE_0023 pfnCreateCommandQueue;

HRESULT APIENTRY* pfnCreateCommandQueue(
             D3D12DDI_HDEVICE                    hDevice,
  _In_ const D3D12DDIARG_CREATECOMMANDQUEUE_0023 *CreateCommandQueue,
             D3D12DDI_HCOMMANDQUEUE              hDrvCommandQueue,
             D3D12DDI_HRTCOMMANDQUEUE            hRTCommandQueue
)
{ ... }
````


## -parameters




### -param D3D12DDI_HDEVICE


### -param *


### -param D3D12DDI_HCOMMANDQUEUE


### -param D3D12DDI_HRTCOMMANDQUEUE








#### - hDevice

The handle of a device.


#### - CreateCommandQueue [in]

An argument used to create a command queue. 


#### - hDrvCommandQueue

The handle of a command queue.


#### - hRTCommandQueue

The handle of the command queue for the driver to use when it calls back into the runtime.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Access this callback function by using a device functions core structure, such as the <b>D3D12DDI_DEVICE_FUNCS_CORE_0003</b> structure.



