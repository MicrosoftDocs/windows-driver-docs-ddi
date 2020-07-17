---
UID: NF:portcls.IDmaChannel.GetAdapterObject
title: IDmaChannel::GetAdapterObject (portcls.h)
description: The GetAdapterObject method returns the DMA channel's hardware adapter object.
tech.root: audio
ms.assetid: 36aeb4c5-4552-4139-bf24-475624e279dc
ms.date: 10/31/2018 
keywords: ["IDmaChannel::GetAdapterObject"]
f1_keywords:
 - "portcls/IDmaChannel.GetAdapterObject"
 - "IDmaChannel.GetAdapterObject"
ms.keywords: IDmaChannel::GetAdapterObject, GetAdapterObject, IDmaChannel.GetAdapterObject, IDmaChannel::GetAdapterObject, IDmaChannel.GetAdapterObject
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level
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
 - COM
api_location: 
 - portcls.h
api_name: 
 - IDmaChannel.GetAdapterObject
product: 
 - Windows
targetos: Windows

---

# IDmaChannel::GetAdapterObject


## -description
The GetAdapterObject method returns the DMA channel's hardware adapter object.

## -returns
This method returns PADAPTER_OBJECT. It returns a pointer to the DMA-channel object's internal adapter object, which is a DMA_ADAPTER structure.


## -remarks
The method returns a pointer to a DMA adapter object that has a system-defined interface to the DMA operations that the hardware supports. The adapter driver can pass this pointer as a parameter to the AllocateCommonBuffer and FreeCommonBuffer functions if the miniport driver needs to allocate its own physically contiguous memory for common buffer blocks. These blocks can be accessed both by DMA hardware and by software running on the processor. 

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)
