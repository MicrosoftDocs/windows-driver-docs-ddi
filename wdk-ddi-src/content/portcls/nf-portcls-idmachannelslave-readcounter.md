---
UID: NF:portcls.IDmaChannelSlave.ReadCounter
title: IDmaChannelSlave::ReadCounter (portcls.h)
description: The ReadCounter method reads the counter of a subordinate DMA object.
tech.root: audio
ms.assetid: e3b67baa-da4b-468b-be74-8b760002b597
ms.date: 10/30/2018
keywords: ["IDmaChannelSlave::ReadCounter"]
f1_keywords:
 - "portcls/IDmaChannelSlave.ReadCounter"
ms.keywords: IDmaChannelSlave::ReadCounter, ReadCounter, IDmaChannelSlave.ReadCounter, IDmaChannelSlave::ReadCounter, IDmaChannelSlave.ReadCounter
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: <=DISPATCH_LEVEL
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
 - IDmaChannelSlave.ReadCounter
product: 
 - Windows
targetos: Windows

---

# IDmaChannelSlave::ReadCounter


## -description

The ReadCounter method reads the counter of a subordinate DMA object.

## -returns
ReadCounter returns the DMA object's counter value as ULONG, which specifies the current byte count. When the object is started, this value is set to the map size (the IDmaChannelSlave::Start method's MapSize parameter). The value decrements until it reaches zero, at which time it is reset to the map size. This process repeats until the DMA object is stopped (by calling the IDmaChannelSlave::Stop method).

## -remarks

## -see-also

[IDmaChannelSlave interface](nn-portcls-idmachannelslave.md)
