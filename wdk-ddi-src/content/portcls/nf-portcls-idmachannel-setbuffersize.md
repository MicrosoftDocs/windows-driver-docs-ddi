---
UID: NF:portcls.IDmaChannel.SetBufferSize
title: IDmaChannel::SetBufferSize
description: The SetBufferSize method sets the DMA channel's current buffer size.
tech.root: audio
ms.assetid: 5adce14a-0791-49a2-9afa-8d7421a39d05
ms.date: 10/31/2018
ms.topic: method
ms.keywords: IDmaChannel::SetBufferSize, SetBufferSize, IDmaChannel.SetBufferSize, IDmaChannel::SetBufferSize, IDmaChannel.SetBufferSize
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
 - IDmaChannel.SetBufferSize
product: 
 - Windows
targetos: Windows

---

# IDmaChannel::SetBufferSize

## -description

The SetBufferSize method sets the DMA channel's current buffer size.

## -parameters

### -param BufferSize

Specifies the buffer's current size in bytes.


## -returns
This method returns void.

## -remarks

The SetBufferSize method is used to change the size of a buffer that was previously allocated by the IDmaChannel::AllocateBuffer method. After the call to AllocateBuffer and before SetBufferSize is called, the IDmaChannel::BufferSize returns the actual size of the allocated buffer. After SetBufferSize is called, BufferSize returns the size specified in the SetBufferSize call. The DMA-channel object does not actually use this value internally. The current buffer size is maintained by the object to allow its various clients to communicate the intended size of the buffer. 


## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)
