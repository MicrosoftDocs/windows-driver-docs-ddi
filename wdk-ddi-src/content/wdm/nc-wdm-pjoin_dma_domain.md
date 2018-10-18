---
UID: NC:wdm.PJOIN_DMA_DOMAIN
title: PJOIN_DMA_DOMAIN
author: windows-driver-content
description: 
ms.assetid: e5cd824e-ab68-4d20-93d5-a84362859e99
ms.date: 
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	wdm.h
api_name: 
-	PJOIN_DMA_DOMAIN
-   JoinDmaDomain
product:
-	Windows
targetos: Windows
---

# PJOIN_DMA_DOMAIN callback function

## -description

This callback function joins the specified DMA domain.

## -prototype

```cpp
//Declaration

PJOIN_DMA_DOMAIN PjoinDmaDomain; 

// Definition

NTSTATUS PjoinDmaDomain 
(
	PDMA_ADAPTER DmaAdapter
	HANDLE DomainHandle
)
{...}

```

## -parameters

### -param DmaAdapter

[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

### -param DomainHandle 

[in] The handle to the DMA domain that the caller previous obtained through [*PGET_DMA_DOMAIN*](nc-wdm-pget_dma_domain.md).

## -returns

Returns STATUS_SUCCESS if the call is successful. Otherwise, returns an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks


## -see-also
