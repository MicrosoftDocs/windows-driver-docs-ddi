---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0032
title: PFND3D12DDI_CREATEVIDEODECODERHEAP_0032
author: windows-driver-content
description: Used to create a video decoder heap.
old-location: display\pfnd3d12ddi_createvideodecoderheap_0032.htm
old-project: display
ms.assetid: EC383086-CE8F-4387-8F92-BEC8215A97DA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
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
req.alt-api: PFND3D12DDI_CREATEVIDEODECODERHEAP_0032
req.alt-loc: d3d12umddi.h
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEVIDEODECODERHEAP_0032 callback



## -description
Used to create a video decoder heap.



## -prototype

````
HRESULT APIENTRY* PFND3D12DDI_CREATEVIDEODECODERHEAP_0032(
             D3D12DDI_HDEVICE                           hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 *pArgs,
             D3D12DDI_HVIDEODECODERHEAP_0032            hDrvVideoDecoderHeap
);
````


## -parameters

### -param hDrvDevice 

The hardware device being processed.


### -param pArgs [in]

The arguments used to create a video decoder heap.


### -param hDrvVideoDecoderHeap 

The video decoder heap.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks
