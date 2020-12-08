---
UID: NF:portcls.IDmaChannel.CopyTo
title: IDmaChannel::CopyTo (portcls.h)
description: The CopyTo method copies sample data to the DMA channel's common buffer from the specified source buffer.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IDmaChannel::CopyTo"]
ms.keywords: IDmaChannel::CopyTo, CopyTo, IDmaChannel.CopyTo, IDmaChannel::CopyTo, IDmaChannel.CopyTo
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
 - IDmaChannel::CopyTo
 - portcls/IDmaChannel::CopyTo
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannel.CopyTo
product:
 - Windows
---

# IDmaChannel::CopyTo


## -description

The CopyTo method copies sample data to the DMA channel's common buffer from the specified source buffer.

## -parameters

### -param Destination

Pointer to the destination buffer, which is located in the DMA channel's common buffer.

### -param Source

Pointer to the source buffer

### -param ByteCount

Specifies the number of bytes to be copied.

## -remarks

The Source and Destination pointers are both kernel-mode virtual addresses. The IDmaChannel::SystemAddress call returns the virtual address of a DMA channel's common buffer.

The Destination parameter points to the beginning of the destination buffer, which occupies ByteCount contiguous bytes in the DMA channel's common buffer.

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)

