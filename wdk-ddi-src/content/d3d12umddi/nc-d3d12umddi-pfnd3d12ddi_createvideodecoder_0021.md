---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODER_0021
title: PFND3D12DDI_CREATEVIDEODECODER_0021
author: windows-driver-content
description: The pfnCreateVideoDecoder callback function creates a video decoder.
old-location: display\pfnd3d12ddi_createvideodecoder.htm
old-project: display
ms.assetid: 5E0B6A5A-FA6E-4722-B442-FE74437224B3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.pfnd3d12ddi_createvideodecoder, pfnCreateVideoDecoder callback function [Display Devices], pfnCreateVideoDecoder, PFND3D12DDI_CREATEVIDEODECODER_0021, PFND3D12DDI_CREATEVIDEODECODER_0021, d3d12umddi/pfnCreateVideoDecoder
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
-	pfnCreateVideoDecoder
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEVIDEODECODER_0021 callback


## -description


The <i>pfnCreateVideoDecoder</i> callback function creates a video decoder.


## -prototype


````
PFND3D12DDI_CREATEVIDEODECODER_0021 pfnCreateVideoDecoder;

HRESULT APIENTRY* pfnCreateVideoDecoder(
             D3D12DDI_HDEVICE                 hDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER *CreateVideoDecoder,
             D3D12DDI_HVIDEODECODER           hDrvVideoDecoder
)
{ ... }
````


## -parameters




### -param hDrvDevice


### -param *pArgs


### -param hDrvVideoDecoder

The handle of a driver video decoder.


#### - hDevice

The handle of the device.


#### - CreateVideoDecoder [in]

The arguments used to create a video decoder.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



