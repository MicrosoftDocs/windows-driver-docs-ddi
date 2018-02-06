---
UID: NS:ndis._NDIS_PD_TRANSMIT_QUEUE_COUNTER
title: "_NDIS_PD_TRANSMIT_QUEUE_COUNTER"
author: windows-driver-content
description: This structure is used to hold counter information for a transmit queue.
old-location: netvista\ndis_pd_transmit_queue_counter.htm
old-project: netvista
ms.assetid: 944E824D-8092-4165-97A6-A35858EA0CEB
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_PD_TRANSMIT_QUEUE_COUNTER structure [Network Drivers Starting with Windows Vista], ndis/NDIS_PD_TRANSMIT_QUEUE_COUNTER, NDIS_PD_TRANSMIT_QUEUE_COUNTER, ndis/PNDIS_PD_TRANSMIT_QUEUE_COUNTER, _NDIS_PD_TRANSMIT_QUEUE_COUNTER, PNDIS_PD_TRANSMIT_QUEUE_COUNTER, netvista.ndis_pd_transmit_queue_counter, PNDIS_PD_TRANSMIT_QUEUE_COUNTER structure pointer [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ndis.h
apiname:
-	NDIS_PD_TRANSMIT_QUEUE_COUNTER
product: Windows
targetos: Windows
req.typenames: NDIS_PD_TRANSMIT_QUEUE_COUNTER
---

# _NDIS_PD_TRANSMIT_QUEUE_COUNTER structure


## -description


This structure is used to hold counter information for a transmit queue.


## -syntax


````
typedef struct _NDIS_PD_TRANSMIT_QUEUE_COUNTER {
  ULONG64 PacketsTransmitted;
  ULONG64 BytesTransmitted;
} NDIS_PD_TRANSMIT_QUEUE_COUNTER, *PNDIS_PD_TRANSMIT_QUEUE_COUNTER;
````


## -struct-fields




### -field PacketsTransmitted

The amount of packets transmitted.


### -field BytesTransmitted

The amount of bytes transmitted.

