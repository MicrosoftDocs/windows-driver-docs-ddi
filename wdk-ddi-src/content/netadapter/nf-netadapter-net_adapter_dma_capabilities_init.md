---
UID: NF:netadapter.NET_ADAPTER_DMA_CAPABILITIES_INIT
title: NET_ADAPTER_DMA_CAPABILITIES_INIT function (netadapter.h)
description: The NET_ADAPTER_DMA_CAPABILITIES_INIT method initializes a NET_ADAPTER_DMA_CAPABILITIES structure.
tech.root: netvista
ms.assetid: 7e1a1622-4479-445e-8672-3dcc9b402679
ms.date: 02/14/2018
keywords: ["NET_ADAPTER_DMA_CAPABILITIES_INIT function"]
f1_keywords:
 - "netadapter/NET_ADAPTER_DMA_CAPABILITIES_INIT"
 - "NET_ADAPTER_DMA_CAPABILITIES_INIT"
ms.keywords: NET_ADAPTER_DMA_CAPABILITIES_INIT
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.25
req.umdf-ver:
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
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- NET_ADAPTER_DMA_CAPABILITIES_INIT
targetos: Windows

---

# NET_ADAPTER_DMA_CAPABILITIES_INIT function


## -description



The **NET_ADAPTER_DMA_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_DMA_CAPABILITIES**](ns-netadapter-_net_adapter_dma_capabilities.md) structure.

## -parameters

### -param DmaCapabilities
A pointer to the driver-allocated **NET_ADAPTER_DMA_CAPABILITIES** structure to be initialized.

### -param DmaEnabler
A DMA enabler object the client driver obtained in a previous call to [**WdfDmaEnablerCreate**](../wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate.md).

## -remarks

The client driver typically calls this method while setting capabilities for its data path, when it is starting a net adapter but before it calls [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also
