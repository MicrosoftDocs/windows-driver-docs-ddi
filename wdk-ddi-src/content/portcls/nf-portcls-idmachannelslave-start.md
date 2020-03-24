---
UID: NF:portcls.IDmaChannelSlave.Start
title: IDmaChannelSlave::Start (portcls.h)
description: The Start method starts a subordinate DMA object.
tech.root: audio
ms.assetid: 35bad0d6-f3ce-48c8-8bf2-f25707378dec
ms.date: 10/30/2018
keywords: ["IDmaChannelSlave::Start"]
f1_keywords:
 - "portcls/IDmaChannelSlave.Start"
ms.keywords: IDmaChannelSlave::Start, Start, IDmaChannelSlave.Start, IDmaChannelSlave::Start, IDmaChannelSlave.Start
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
 - IDmaChannelSlave.Start
product: 
 - Windows
targetos: Windows

---

# IDmaChannelSlave::Start


## -description

The Start method starts a subordinate DMA object.

## -parameters

### -param MapSize

Specifies the number of bytes of the allocated buffer that are to be mapped. The map size must not exceed the size of the buffer allocated in the call to IDmaChannel::AllocateBuffer.


### -param WriteToDevice

Specifies the direction of data movement. If TRUE, the data is to be moved from the buffer to the device. If FALSE, the data is to be moved from the device to the buffer.


## -returns
This method returns NTSTATUS. It returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. If the caller attempts to start a channel that is already started, the method returns immediately with error code STATUS_UNSUCCESSFUL.

## -remarks
The method first sets up map registers to map the first MapSize bytes of the allocated buffer for the adapter object. Next, the method starts a DMA transfer of the number of bytes specified in MapSize.

For more information about this method, see [IDmaChannel::BufferSize](nf-portcls-idmachannel-buffersize.md) and [IDmaChannelSlave::ReadCounter](nf-portcls-idmachannelslave-readcounter.md).

## -see-also

[IDmaChannelSlave interface](nn-portcls-idmachannelslave.md)
