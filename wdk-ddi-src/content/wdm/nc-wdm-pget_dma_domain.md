---
UID: NC:wdm.PGET_DMA_DOMAIN
title: PGET_DMA_DOMAIN (wdm.h)
description: 
tech.root: kernel
ms.date: 10/19/2018
keywords: ["PGET_DMA_DOMAIN callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - PGET_DMA_DOMAIN
 - wdm/PGET_DMA_DOMAIN
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PGET_DMA_DOMAIN
---

# PGET_DMA_DOMAIN callback function


## -description

This callback function gets the handle to the DMA domain.

## -parameters

### -param DmaAdapter: 

[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

## -returns

Returns HANDLE to the DMA domain.

## -prototype

```cpp
//Declaration

PGET_DMA_DOMAIN PgetDmaDomain; 

// Definition

HANDLE PgetDmaDomain 
(
	PDMA_ADAPTER DmaAdapter
)
{...}

PGET_DMA_DOMAIN 


```

## -remarks

## -see-also

