---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021
title: PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021
author: windows-driver-content
description: The pfnCalcPrivateVideoDecoderSize callback function calculates the size of a private video decoder.
old-location: display\pfnd3d12ddi_calcprivatevideodecodersize.htm
old-project: display
ms.assetid: 29A0CB0F-3469-4EF5-8C5B-132321F6C8E8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_calcprivatevideodecodersize, pfnCalcPrivateVideoDecoderSize callback function [Display Devices], pfnCalcPrivateVideoDecoderSize, PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021, PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021, d3d12umddi/pfnCalcPrivateVideoDecoderSize
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
-	pfnCalcPrivateVideoDecoderSize
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 callback


## -description


The <i>pfnCalcPrivateVideoDecoderSize</i> callback function calculates the size of a private video decoder.


## -prototype


````
PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021 pfnCalcPrivateVideoDecoderSize;

SIZE_T APIENTRY* pfnCalcPrivateVideoDecoderSize(
             D3D12DDI_HDEVICE                  hDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER  *CreateVideoDecoder
)
{ ... }
````


## -parameters




### -param hDrvDevice



### -param *pArgs






#### - CreateVideoDecoder [in]

The arguments used to create a video decoder.


#### - hDevice

The handle of a device. 


## -remarks


The runtime allocates memory for storing the driver CPU object that represents the video decoder.  This method is used to calculate the driver object size.


