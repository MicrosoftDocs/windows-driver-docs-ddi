---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODER_0032
title: PFND3D12DDI_CREATEVIDEODECODER_0032
author: windows-driver-content
description: Used to create a video decoder.
old-location: display\pfnd3d12ddi_createvideodecoder_0032.htm
old-project: display
ms.assetid: F3E8FB7A-A25B-47CE-8B14-9AE8737930D4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_createvideodecoder_0032, PFND3D12DDI_CREATEVIDEODECODER_0032 callback function [Display Devices], PFND3D12DDI_CREATEVIDEODECODER_0032, d3d12umddi/PFND3D12DDI_CREATEVIDEODECODER_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CREATEVIDEODECODER_0032
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEVIDEODECODER_0032 callback


## -description


Used to create a video decoder.


## -prototype


````
HRESULT APIENTRY* PFND3D12DDI_CREATEVIDEODECODER_0032(
             D3D12DDI_HDEVICE                      hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER_0032 *pArgs,
             D3D12DDI_HVIDEODECODER_0020           hDrvVideoDecoder
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to create a video decoder.


### -param hDrvVideoDecoder

The video decoder.


## -returns



Returns STATUS_SUCCESS if completed successfully.



