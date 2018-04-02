---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021
title: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021
author: windows-driver-content
description: The pfnCalcPrivateVideoProcessorSize callback function calculates the size of the private video processor.
old-location: display\pfnd3d12ddi_calcprivatevideoprocessorsize.htm
old-project: display
ms.assetid: F1ED5176-4F50-44DA-96B3-5E133A236461
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021, d3d12umddi/pfnCalcPrivateVideoProcessorSize, display.pfnd3d12ddi_calcprivatevideoprocessorsize, pfnCalcPrivateVideoProcessorSize, pfnCalcPrivateVideoProcessorSize callback function [Display Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnCalcPrivateVideoProcessorSize
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021 callback


## -description


The <i>pfnCalcPrivateVideoProcessorSize</i> callback function calculates the size of the private video processor.


## -parameters




### -param hDrvDevice

The handler of a device.


### -param *pArgs [in]

The arguments used to create a video processor.


## -remarks



The  runtime allocates memory for storing the driver CPU object that represents the video processor.  This method is used to calculate the driver object size.



