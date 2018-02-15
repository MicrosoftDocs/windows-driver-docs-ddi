---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0021
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0021
author: windows-driver-content
description: The pfnCreateVideoProcessor callback function creates a video processor.
old-location: display\pfnd3d12ddi_createvideoprocessor.htm
old-project: display
ms.assetid: 4F1AA75F-DDC7-490B-8CE2-590691991234
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_createvideoprocessor, pfnCreateVideoProcessor callback function [Display Devices], pfnCreateVideoProcessor, PFND3D12DDI_CREATEVIDEOPROCESSOR_0021, PFND3D12DDI_CREATEVIDEOPROCESSOR_0021, d3d12umddi/pfnCreateVideoProcessor
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
-	pfnCreateVideoProcessor
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback


## -description


The <i>pfnCreateVideoProcessor</i> callback function creates a video processor.


## -prototype


````
PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 pfnCreateVideoProcessor;

HRESULT  APIENTRY* pfnCreateVideoProcessor(
   D3D12DDI_HDEVICE         hDrvDevice,
   D3D12DDI_HVIDEOPROCESSOR hDrvVideoProcessor
)
{ ... }
````


## -parameters




### -param hDrvDevice

The handle of a device driver.


### -param *pArgs


### -param hDrvVideoProcessor

The handle of a video processor.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



