---
UID: NS:ndis._NDIS_PD_COUNTER_VALUE
title: "_NDIS_PD_COUNTER_VALUE"
author: windows-driver-content
description: This structure is used to hold a counter value for a queue or filter counter.
old-location: netvista\ndis_pd_counter_value.htm
old-project: netvista
ms.assetid: 0C2424C5-F6EE-4D07-B5C3-CEC3520AFFDC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_PD_COUNTER_VALUE union [Network Drivers Starting with Windows Vista], PNDIS_PD_COUNTER_VALUE, ndis/PNDIS_PD_COUNTER_VALUE, PNDIS_PD_COUNTER_VALUE union pointer [Network Drivers Starting with Windows Vista], *PNDIS_PD_COUNTER_VALUE, _NDIS_PD_COUNTER_VALUE, ndis/NDIS_PD_COUNTER_VALUE, NDIS_PD_COUNTER_VALUE, netvista.ndis_pd_counter_value
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
-	NDIS_PD_COUNTER_VALUE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_COUNTER_VALUE, *PNDIS_PD_COUNTER_VALUE
---

# _NDIS_PD_COUNTER_VALUE structure


## -description


This structure is used to hold a counter value for a queue or filter counter.


## -syntax


````
typedef union _NDIS_PD_COUNTER_VALUE {
  NDIS_PD_RECEIVE_QUEUE_COUNTER  ReceiveQueue;
  NDIS_PD_TRANSMIT_QUEUE_COUNTER TransmitQueue;
  NDIS_PD_FILTER_COUNTER         Filter;
} NDIS_PD_COUNTER_VALUE, *PNDIS_PD_COUNTER_VALUE;
````


## -struct-fields




### -field ReceiveQueue

See <a href="..\ndis\ns-ndis-_ndis_pd_receive_queue_counter.md">NDIS_PD_RECEIVE_QUEUE_COUNTER</a>.


### -field TransmitQueue

See <a href="..\ndis\ns-ndis-_ndis_pd_transmit_queue_counter.md">NDIS_PD_TRANSMIT_QUEUE_COUNTER</a>.


### -field Filter

See <a href="..\ndis\ns-ndis-_ndis_pd_filter_counter.md">NDIS_PD_FILTER_COUNTER</a>.

