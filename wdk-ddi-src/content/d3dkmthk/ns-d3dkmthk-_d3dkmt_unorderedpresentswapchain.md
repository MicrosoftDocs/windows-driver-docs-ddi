---
UID: NS:d3dkmthk._D3DKMT_UNORDEREDPRESENTSWAPCHAIN
title: "_D3DKMT_UNORDEREDPRESENTSWAPCHAIN"
author: windows-driver-content
description: Used to store information about the swapchain being presented.
old-location: display\d3dkmt-unorderedpresentswapchain.htm
old-project: display
ms.assetid: c8b13348-71a6-4981-8c99-6368fa0f01ff
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure [Display Devices], d3dkmthk/D3DKMT_UNORDEREDPRESENTSWAPCHAIN, D3DKMT_UNORDEREDPRESENTSWAPCHAIN, display.d3dkmt-unorderedpresentswapchain, _D3DKMT_UNORDEREDPRESENTSWAPCHAIN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_UNORDEREDPRESENTSWAPCHAIN
product: Windows
targetos: Windows
req.typenames: D3DKMT_UNORDEREDPRESENTSWAPCHAIN
---

# _D3DKMT_UNORDEREDPRESENTSWAPCHAIN structure


## -description


Used to store information about the swapchain being presented.


## -syntax


````
typedef struct _D3DKMT_UNORDEREDPRESENTSWAPCHAIN {
  HANDLE hNtSwapChain;
  BOOL   bProducer;
  UINT   PresentBufferIdx;
  UINT   MetaDataSize;
  PVOID  pMetaData;
} D3DKMT_UNORDEREDPRESENTSWAPCHAIN;
````


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

