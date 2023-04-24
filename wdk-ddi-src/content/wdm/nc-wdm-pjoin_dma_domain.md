---
UID: NC:wdm.PJOIN_DMA_DOMAIN
title: PJOIN_DMA_DOMAIN (wdm.h)
description: The PJOIN_DMA_DOMAIN callback function joins the specified DMA domain.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["PJOIN_DMA_DOMAIN callback function"]
req.header: wdm.h
req.include-header: Wdm.h
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
 - PJOIN_DMA_DOMAIN
 - wdm/PJOIN_DMA_DOMAIN
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PJOIN_DMA_DOMAIN
---

## -description

The PJOIN_DMA_DOMAIN callback function joins the specified DMA domain.

## -parameters

### -param DmaAdapter [in]

A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

### -param DomainHandle [in]

The handle to the DMA domain that the caller previous obtained through [*PGET_DMA_DOMAIN*](nc-wdm-pget_dma_domain.md).

## -returns

Returns STATUS_SUCCESS if the call is successful. Otherwise, returns an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
