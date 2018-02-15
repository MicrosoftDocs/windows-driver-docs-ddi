---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032
title: PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032
author: windows-driver-content
description: Used to destroy a video decoder heap.
old-location: display\pfnd3d12ddi_destroyvideodecoderheap_0032.htm
old-project: display
ms.assetid: EFB7D67D-1900-4182-B604-8C0A183B118D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_destroyvideodecoderheap_0032, PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032 callback function [Display Devices], PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032, d3d12umddi/PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032
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
-	PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032 callback


## -description


Used to destroy a video decoder heap.


## -prototype


````
VOID APIENTRY* PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032(
   D3D12DDI_HDEVICE                hDrvDevice,
   D3D12DDI_HVIDEODECODERHEAP_0032 hDrvVideoDecoderHeap
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param hDrvVideoDecoderHeap

The video decoder heap.


## -returns



This callback function does not return a value.



