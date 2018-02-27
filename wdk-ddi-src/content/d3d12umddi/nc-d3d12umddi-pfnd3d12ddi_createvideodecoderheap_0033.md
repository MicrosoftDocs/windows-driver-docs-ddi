---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
title: PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
author: windows-driver-content
description: Used to create a video decoder heap.
old-location: display\pfnd3d12ddi_createvideodecoderheap_0033_.htm
old-project: display
ms.assetid: BCCDBC42-FE6B-49C6-9E95-F0CF7F5CCB2E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D12DDI_CREATEVIDEODECODERHEAP_0033, PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0033, display.pfnd3d12ddi_createvideodecoderheap_0033_
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback


## -description


Used to create a video decoder heap.


## -prototype


````
HRESULT APIENTRY* PFND3D12DDI_CREATEVIDEODECODERHEAP_0033(
             D3D12DDI_HDEVICE                           hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 *pArgs,
             D3D12DDI_HVIDEODECODERHEAP_0032            hDrvVideoDecoderHeap
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *


### -param hDrvVideoDecoderHeap

The video decoder heap.


#### - pArgs [in]

The arguments used to create a video decoder heap.


## -returns



Returns STATUS_SUCCESS if completed successfully.



