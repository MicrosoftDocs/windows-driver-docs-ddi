---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
title: PFND3D12DDI_CREATEVIDEODECODERHEAP_0033
author: windows-driver-content
description: Used to create a video decoder heap.
old-location: display\pfnd3d12ddi_createvideodecoderheap_0033_.htm
ms.assetid: BCCDBC42-FE6B-49C6-9E95-F0CF7F5CCB2E
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_CREATEVIDEODECODERHEAP_0033, PFND3D12DDI_CREATEVIDEODECODERHEAP_0033  callback, PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEODECODERHEAP_0033, display.pfnd3d12ddi_createvideodecoderheap_0033_
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATEVIDEODECODERHEAP_0033 callback function


## -description


Used to create a video decoder heap.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *

pArgs [in]

The arguments used to create a video decoder heap.

### -param hDrvVideoDecoderHeap

The video decoder heap.




## -returns



Returns STATUS_SUCCESS if completed successfully.



