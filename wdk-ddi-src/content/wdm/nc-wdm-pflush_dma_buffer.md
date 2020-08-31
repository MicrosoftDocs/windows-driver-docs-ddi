---
UID: NC:wdm.PFLUSH_DMA_BUFFER
title: PFLUSH_DMA_BUFFER (wdm.h)
description: 
ms.assetid: f51783e4-9956-4608-ba45-affdafda2416
ms.date: 10/19/2018
keywords: ["PFLUSH_DMA_BUFFER callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - PFLUSH_DMA_BUFFER
 - wdm/PFLUSH_DMA_BUFFER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - PFLUSH_DMA_BUFFER
 - FlushDmaBuffer
---

# PFLUSH_DMA_BUFFER callback function


## -description

The callback routine flushes any data remaining in the memory region described by an MDL.

## -parameters

### -param DmaAdapter: 

[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.

### -param Mdl: 

[in] A pointer to the MDL that describes the buffer previously passed in the driver's call to [*MapTransfer*](nc-wdm-pmap_transfer.md).

### -param ReadOperation: 

[in] Specifies TRUE if the flush is being performed for a read operation, and FALSE for a write operation. For more information, see the following Remarks section.

## -returns

Returns STATUS_SUCCESS if the call is successful. Otherwise, returns an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

PFLUSH_DMA_BUFFER PflushDmaBuffer; 

// Definition

NTSTATUS PflushDmaBuffer 
(
	PDMA_ADAPTER DmaAdapter
	PMDL Mdl
	BOOLEAN ReadOperation
)
{...}

```

## -remarks

## -see-also

[Flushing Cached Data during DMA Operations](https://docs.microsoft.com/windows-hardware/drivers/kernel/flushing-cached-data-during-dma-operations)

