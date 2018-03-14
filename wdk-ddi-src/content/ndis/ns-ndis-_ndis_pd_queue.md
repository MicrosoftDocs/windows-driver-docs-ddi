---
UID: NS:ndis._NDIS_PD_QUEUE
title: "_NDIS_PD_QUEUE"
author: windows-driver-content
description: This structure represents a provider's receive or transmit queue.
old-location: netvista\ndis_pd_queue.htm
old-project: netvista
ms.assetid: 5405A9A6-243B-4E80-85D7-46C6FCC8339F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDIS_PD_QUEUE, NDIS_PD_QUEUE structure [Network Drivers Starting with Windows Vista], PNDIS_PD_QUEUE, PNDIS_PD_QUEUE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_QUEUE, ndis/NDIS_PD_QUEUE, ndis/PNDIS_PD_QUEUE, netvista.ndis_pd_queue
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
-	NDIS_PD_QUEUE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE, NDIS_PD_QUEUE
---

# _NDIS_PD_QUEUE structure


## -description


This structure represents a provider's receive or transmit queue


## -syntax


````
typedef struct _NDIS_PD_QUEUE {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  const NDIS_PD_QUEUE_DISPATCH *Dispatch;
  PVOID                        PDPlatformReserved[2];
  PVOID                        PDClientReserved[2];
} NDIS_PD_QUEUE, *PNDIS_PD_QUEUE;
````


## -struct-fields




### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_QUEUE</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_PD_TRANSMIT_QUEUE</b> or <b>NDIS_OBJECT_TYPE_PD_RECEIVE_QUEUE</b></li>
<li><b>Revision</b> = <b>NDIS_PD_QUEUE_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_QUEUE_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field Dispatch

See <a href="..\ndis\ns-ndis-_ndis_pd_queue_dispatch.md">NDIS_PD_QUEUE_DISPATCH</a>.


### -field PDPlatformReserved

Reserved for the platform.


### -field PDClientReserved

Reserved for the client.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


