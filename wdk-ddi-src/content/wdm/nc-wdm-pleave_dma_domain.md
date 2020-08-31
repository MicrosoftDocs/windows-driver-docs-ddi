---
UID: NC:wdm.PLEAVE_DMA_DOMAIN
title: PLEAVE_DMA_DOMAIN (wdm.h)
description: 
ms.assetid: 3bcd31e2-548b-44c3-a301-351c4adc18d6
ms.date: 10/19/2018
keywords: ["PLEAVE_DMA_DOMAIN callback function"]
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
 - PLEAVE_DMA_DOMAIN
 - wdm/PLEAVE_DMA_DOMAIN
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PLEAVE_DMA_DOMAIN
 - LeaveDmaDomain
---

# PLEAVE_DMA_DOMAIN callback function


## -description

This callback function joins the specified DMA domain.

## -parameters

### -param DmaAdapter

[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

## -returns

Returns STATUS_SUCCESS if the call is successful. Otherwise, returns an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

PLEAVE_DMA_DOMAIN PleaveDmaDomain; 

// Definition

NTSTATUS PleaveDmaDomain 
(
	PDMA_ADAPTER DmaAdapter
)
{...}

```

## -remarks

## -see-also

