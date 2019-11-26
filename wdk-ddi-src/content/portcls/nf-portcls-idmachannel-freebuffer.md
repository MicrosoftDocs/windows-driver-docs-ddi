---
UID: NF:portcls.IDmaChannel.FreeBuffer
title: IDmaChannel::FreeBuffer (portcls.h)
description: The FreeBuffer method frees the buffer that was allocated by the previous call to IDmaChannel::AllocateBuffer.
tech.root: audio
ms.assetid: 151e5da1-e78a-4f72-a132-87ae9f743330
ms.date: 10/31/2018 
ms.topic: method
f1_keywords:
 - "portcls/IDmaChannel.FreeBuffer"
ms.keywords: IDmaChannel::FreeBuffer, FreeBuffer, IDmaChannel.FreeBuffer, IDmaChannel::FreeBuffer, IDmaChannel.FreeBuffer
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IDmaChannel.FreeBuffer
product: 
 - Windows
targetos: Windows

---

# IDmaChannel::FreeBuffer


## -description

The FreeBuffer method frees the buffer that was allocated by the previous call to IDmaChannel::AllocateBuffer.

## -remarks

Because the buffer is automatically freed when the DMA-channel object is deleted, the FreeBuffer method is not typically used.

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)
