---
UID: NF:netadapter.NET_ADAPTER_DMA_CAPABILITIES_INIT
title: NET_ADAPTER_DMA_CAPABILITIES_INIT function
author: windows-driver-content
description: The NET_ADAPTER_DMA_CAPABILITIES_INIT method initializes a NET_ADAPTER_DMA_CAPABILITIES structure.
ms.assetid: 7e1a1622-4479-445e-8672-3dcc9b402679
ms.author: windowsdriverdev
ms.date: 02/14/2018
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	NET_ADAPTER_DMA_CAPABILITIES_INIT
product: Windows
targetos: Windows

---

# NET_ADAPTER_DMA_CAPABILITIES_INIT function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_ADAPTER_DMA_CAPABILITIES_INIT** method initializes a [**NET_ADAPTER_DMA_CAPABILITIES**](ns-netadapter-_net_adapter_dma_capabilities.md) structure.

## -parameters

### -param DmaCapabilities
A pointer to the driver-allocated **NET_ADAPTER_DMA_CAPABILITIES** structure to be initialized.

### -param DmaEnabler
A DMA enabler object the client driver obtained in a previous call to [**WdfDmaEnablerCreate**](../wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate.md).

## -returns
This method does not return a value.

## -remarks

The client driver typically calls this method while setting capabilities for its data path, when it is starting a net adapter but before it calls [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also