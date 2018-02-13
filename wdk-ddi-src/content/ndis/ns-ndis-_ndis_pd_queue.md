---
UID: NS:ndis._NDIS_PD_QUEUE
title: "_NDIS_PD_QUEUE"
author: windows-driver-content
description: This structure represents a provider's receive or transmit queue.
old-location: netvista\ndis_pd_queue.htm
old-project: netvista
ms.assetid: 5405A9A6-243B-4E80-85D7-46C6FCC8339F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NDIS_PD_QUEUE, netvista.ndis_pd_queue, PNDIS_PD_QUEUE structure pointer [Network Drivers Starting with Windows Vista], NDIS_PD_QUEUE structure [Network Drivers Starting with Windows Vista], PNDIS_PD_QUEUE, _NDIS_PD_QUEUE, NDIS_PD_QUEUE, ndis/PNDIS_PD_QUEUE
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
-	NDIS_PD_QUEUE
product: Windows
targetos: Windows
req.typenames: NDIS_PD_QUEUE
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_QUEUE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

