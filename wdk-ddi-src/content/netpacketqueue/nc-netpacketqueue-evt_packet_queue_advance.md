---
UID: NC:netpacketqueue.EVT_PACKET_QUEUE_ADVANCE
title: EVT_PACKET_QUEUE_ADVANCE
author: windows-driver-content
description: 
ms.assetid: d4d6becc-ae41-451d-939d-c4169456adb7
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netpacketqueue.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netpacketqueue.h
api_name: 
-	EVT_PACKET_QUEUE_ADVANCE
product: Windows
targetos: Windows
---

# EVT_PACKET_QUEUE_ADVANCE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

EVT_PACKET_QUEUE_ADVANCE EvtPacketQueueAdvance; 

// Definition

VOID EvtPacketQueueAdvance 
(
	NETPACKETQUEUE PacketQueue
)
{...}

```

## -parameters

### -param PacketQueue: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also