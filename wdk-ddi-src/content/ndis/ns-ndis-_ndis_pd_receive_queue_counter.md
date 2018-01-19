---
UID: NS:ndis._NDIS_PD_RECEIVE_QUEUE_COUNTER
title: _NDIS_PD_RECEIVE_QUEUE_COUNTER
author: windows-driver-content
description: This structure is used to hold counter information for a receive queue.
old-location: netvista\ndis_pd_receive_queue_counter.htm
old-project: netvista
ms.assetid: E42705A4-D018-435E-BA98-3EE5BA5EDE66
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_PD_RECEIVE_QUEUE_COUNTER, NDIS_PD_RECEIVE_QUEUE_COUNTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PD_RECEIVE_QUEUE_COUNTER
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: NDIS_PD_RECEIVE_QUEUE_COUNTER
---

# _NDIS_PD_RECEIVE_QUEUE_COUNTER structure



## -description
This structure is used to hold counter information for a receive queue.



## -syntax

````
typedef struct _NDIS_PD_RECEIVE_QUEUE_COUNTER {
  ULONG64 PacketsReceived;
  ULONG64 BytesReceived;
  ULONG64 PacketsDropped;
} NDIS_PD_RECEIVE_QUEUE_COUNTER, *PNDIS_PD_RECEIVE_QUEUE_COUNTER;
````


## -struct-fields

### -field PacketsReceived

The amount of packets received.


### -field BytesReceived

The amount of bytes received.


### -field PacketsDropped

The amount of packets dropped.


## -remarks
