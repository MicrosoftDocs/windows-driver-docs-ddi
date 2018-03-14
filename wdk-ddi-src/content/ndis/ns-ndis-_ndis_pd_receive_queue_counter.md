---
UID: NS:ndis._NDIS_PD_RECEIVE_QUEUE_COUNTER
title: "_NDIS_PD_RECEIVE_QUEUE_COUNTER"
author: windows-driver-content
description: This structure is used to hold counter information for a receive queue.
old-location: netvista\ndis_pd_receive_queue_counter.htm
old-project: netvista
ms.assetid: E42705A4-D018-435E-BA98-3EE5BA5EDE66
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_PD_RECEIVE_QUEUE_COUNTER, NDIS_PD_RECEIVE_QUEUE_COUNTER structure [Network Drivers Starting with Windows Vista], PNDIS_PD_RECEIVE_QUEUE_COUNTER, PNDIS_PD_RECEIVE_QUEUE_COUNTER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_RECEIVE_QUEUE_COUNTER, ndis/NDIS_PD_RECEIVE_QUEUE_COUNTER, ndis/PNDIS_PD_RECEIVE_QUEUE_COUNTER, netvista.ndis_pd_receive_queue_counter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_RECEIVE_QUEUE_COUNTER
product: Windows
targetos: Windows
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

