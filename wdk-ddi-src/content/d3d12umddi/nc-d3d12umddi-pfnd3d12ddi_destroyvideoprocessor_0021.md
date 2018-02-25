---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021
title: PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021
author: windows-driver-content
description: The pfnDestroyVideoProcessor callback function destroys a video processor.
old-location: display\pfnd3d12ddi_destroyvideoprocessor.htm
old-project: display
ms.assetid: 93C1FA5F-064F-41AC-B854-FF59A5CC172C
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021, d3d12umddi/pfnDestroyVideoProcessor, display.pfnd3d12ddi_destroyvideoprocessor, pfnDestroyVideoProcessor, pfnDestroyVideoProcessor callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
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
-	pfnDestroyVideoProcessor
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021 callback


## -description


The <i>pfnDestroyVideoProcessor</i> callback function destroys a video processor.


## -prototype


````
PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021 pfnDestroyVideoProcessor;

VOID APIENTRY* pfnDestroyVideoProcessor(
   D3D12DDI_HDEVICE         hDrvDevice,
   D3D12DDI_HVIDEOPROCESSOR hDrvVideoProcessor
)
{ ... }
````


## -parameters




### -param hDrvDevice

The handle of a device driver.


### -param hDrvVideoProcessor

The handle of a video processor.


## -returns



This callback function does not return a value.



