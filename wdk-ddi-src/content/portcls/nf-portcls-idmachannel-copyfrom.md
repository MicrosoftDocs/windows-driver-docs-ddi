---
UID: NF:portcls.IDmaChannel.CopyFrom
title: IDmaChannel::CopyFrom (portcls.h)
description: The CopyFrom method copies sample data from the DMA channel's common buffer to the specified destination buffer.
tech.root: audio
ms.assetid: 4def160a-db98-4315-87d4-beb69e650461
ms.date: 10/31/2018 
ms.topic: method
ms.keywords: IDmaChannel::CopyFrom, CopyFrom, IDmaChannel.CopyFrom, IDmaChannel::CopyFrom, IDmaChannel.CopyFrom
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
 - IDmaChannel.CopyFrom
product: 
 - Windows
targetos: Windows

---

# IDmaChannel::CopyFrom


## -description

The CopyFrom method copies sample data from the DMA channel's common buffer to the specified destination buffer.

## -parameters

### -param Destination
Pointer to the destination buffer


### -param Source
Pointer to the source buffer, which is located in the DMA channel's common buffer.



### -param ByteCount
Specifies the number of bytes to be copied.



## -returns
This method returns void.

## -remarks

The Source and Destination pointers are both kernel-mode virtual addresses. The IDmaChannel::SystemAddress call returns the virtual address of a DMA channel's common buffer.

The Source parameter points to the beginning of the source buffer, which occupies ByteCount contiguous bytes in the DMA channel's common buffer.


## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)
