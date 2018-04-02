---
UID: NS:d3dkmthk._D3DKMT_UNORDEREDPRESENTSWAPCHAIN
title: "_D3DKMT_UNORDEREDPRESENTSWAPCHAIN"
author: windows-driver-content
description: Used to store information about the swapchain being presented.
old-location: display\d3dkmt-unorderedpresentswapchain.htm
old-project: display
ms.assetid: c8b13348-71a6-4981-8c99-6368fa0f01ff
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_UNORDEREDPRESENTSWAPCHAIN, D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure [Display Devices], _D3DKMT_UNORDEREDPRESENTSWAPCHAIN, d3dkmthk/D3DKMT_UNORDEREDPRESENTSWAPCHAIN, display.d3dkmt-unorderedpresentswapchain
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_UNORDEREDPRESENTSWAPCHAIN
product: Windows
targetos: Windows
req.typenames: D3DKMT_UNORDEREDPRESENTSWAPCHAIN
---

# _D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure


## -description


Used to store information about the swapchain being presented.


## -struct-fields




### -field hNtSwapChain

NT handle for the swapchain in this process.


### -field bProducer

Indicates if producer or consumer.


### -field PresentBufferIdx

Index of the buffer to present.


### -field MetaDataSize

Size of the metadata.


### -field pMetaData

A pointer to the metadata for the frame.

