---
UID: NF:portcls.IDmaChannel.AllocateBuffer
title: IDmaChannel::AllocateBuffer (portcls.h)
description: The AllocateBuffer method allocates a common buffer that can be accessed by the port driver and DMA hardware.
tech.root: audio
ms.assetid: 5a1752fd-35e1-4ce1-9322-e4202705cb29
ms.date: 10/31/2018
keywords: ["IDmaChannel::AllocateBuffer"]
ms.keywords: IDmaChannel::AllocateBuffer, AllocateBuffer, IDmaChannel.AllocateBuffer, IDmaChannel::AllocateBuffer, IDmaChannel.AllocateBuffer
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
targetos: Windows
f1_keywords:
 - IDmaChannel::AllocateBuffer
 - portcls/IDmaChannel::AllocateBuffer
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannel.AllocateBuffer
product:
 - Windows
---

# IDmaChannel::AllocateBuffer


## -description

The AllocateBuffer method allocates a common buffer that can be accessed by the port driver and DMA hardware.

## -parameters

### -param BufferSize

Specifies the size in bytes of the buffer to be allocated.

### -param PhysicalAddressConstraint

Specifies an optional constraint to place on the physical address of the buffer. If this parameter is non-NULL, only the bits that are set in the constraint address will vary from the beginning to the end of the buffer. For example, to request a buffer that does not cross a 64-kilobyte boundary, specify the physical address constraint 0x000000000000FFFF.

## -returns

This method returns NTSTATUS. AllocateBuffer returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

This method must be called only once following the creation of the DMA-channel object unless the previously allocated buffer is first freed by calling FreeBuffer.

## -see-also

[IDmaChannel](nn-portcls-idmachannel.md)

