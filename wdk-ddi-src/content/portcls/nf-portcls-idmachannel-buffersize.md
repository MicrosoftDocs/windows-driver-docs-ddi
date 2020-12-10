---
UID: NF:portcls.IDmaChannel.BufferSize
title: IDmaChannel::BufferSize (portcls.h)
description: The BufferSize method returns the size in bytes of the DMA channel's data buffer.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IDmaChannel::BufferSize"]
ms.keywords: IDmaChannel::BufferSize, BufferSize, IDmaChannel.BufferSize, IDmaChannel::BufferSize, IDmaChannel.BufferSize
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
targetos: Windows
f1_keywords:
 - IDmaChannel::BufferSize
 - portcls/IDmaChannel::BufferSize
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannel.BufferSize
product:
 - Windows
---

# IDmaChannel::BufferSize

## -description

The BufferSize method returns the size in bytes of the DMA channel's data buffer.

## -returns

This method returns ULONG which is the size in bytes of the buffer.

## -remarks

The BufferSize method returns the buffer size that was set by the previous call to IDmaChannel::SetBufferSize. If SetBufferSize has not been called since the IDmaChannel::AllocateBuffer call, BufferSize returns the allocated buffer size. The DMA-channel object does not actually use this value internally. This value is maintained by the object to allow its various clients to communicate the intended size of the buffer. This call is often used to obtain the map-size parameter to the IDmaChannelSlave::Start method.

> [!NOTE]
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the [Microsoft style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)
