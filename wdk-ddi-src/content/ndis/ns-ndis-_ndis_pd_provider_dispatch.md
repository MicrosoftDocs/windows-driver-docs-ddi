---
UID: NS:ndis._NDIS_PD_PROVIDER_DISPATCH
title: "_NDIS_PD_PROVIDER_DISPATCH"
author: windows-driver-content
description: This structure is used as input for the OID_PD_OPEN_PROVIDER and serves as a container for all the provider's driver routines.
old-location: netvista\ndis_pd_provider_dispatch.htm
old-project: netvista
ms.assetid: E93B8A07-7C06-470B-9B26-8D59C2685D2C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_pd_provider_dispatch, NDIS_PD_PROVIDER_DISPATCH structure [Network Drivers Starting with Windows Vista], NDIS_PD_PROVIDER_DISPATCH, ndis/NDIS_PD_PROVIDER_DISPATCH, PNDIS_PD_PROVIDER_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], ndis/PNDIS_PD_PROVIDER_DISPATCH, PNDIS_PD_PROVIDER_DISPATCH, _NDIS_PD_PROVIDER_DISPATCH
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
-	NDIS_PD_PROVIDER_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDIS_PD_PROVIDER_DISPATCH
---

# _NDIS_PD_PROVIDER_DISPATCH structure


## -description


This structure is used as input for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931852">OID_PD_OPEN_PROVIDER</a> and serves as a container for all the provider's driver routines.


## -syntax


````
typedef struct _NDIS_PD_PROVIDER_DISPATCH {
  NDIS_OBJECT_HEADER                     Header;
  ULONG                                  Flags;
  NDIS_PD_ALLOCATE_QUEUE_HANDLER         NdisPDAllocateQueue;
  NDIS_PD_FREE_QUEUE_HANDLER             NdisPDFreeQueue;
  NDIS_PD_ON_RSS_RECEIVE_QUEUES_HANDLER  NdisPDOnRssReceiveQueues;
  NDIS_PD_OFF_RSS_RECEIVE_QUEUES_HANDLER NdisPDOffRssReceiveQueues;
  NDIS_PD_ALLOCATE_COUNTER_HANDLER       NdisPDAllocateCounter;
  NDIS_PD_FREE_COUNTER_HANDLER           NdisPDFreeCounter;
  NDIS_PD_QUERY_COUNTER_HANDLER          NdisPDQueryCounter;
  NDIS_PD_SET_RECEIVE_FILTER_HANDLER     NdisPDSetReceiveFilter;
  NDIS_PD_CLEAR_RECEIVE_FILTER_HANDLER   NdisPDClearReceiveFilter;
} NDIS_PD_PROVIDER_DISPATCH, *PNDIS_PD_PROVIDER_DISPATCH;
````


## -struct-fields




#### - Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_PROVIDER_DISPATCH</b> structure. Set the members of this structure as follows:
<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_PROVIDER_DISPATCH_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_PROVIDER_DISPATCH_REVISION_1</b></li>
</ul>

#### - Flags

This member is reserved and must be set to 0 by the provider.


#### - NdisPDAllocateQueue

See <a href="..\ndis\nc-ndis-ndis_pd_allocate_queue.md">NdisPDAllocateQueue</a>.


#### - NdisPDFreeQueue

See <a href="..\ndis\nc-ndis-ndis_pd_free_queue.md">NdisPDFreeQueue</a>.


### -field NdisPDAcquireReceiveQueues

 


### -field NdisPDReleaseReceiveQueues

 


#### - NdisPDAllocateCounter

See <a href="..\ndis\nc-ndis-ndis_pd_allocate_counter.md">NdisPDAllocateCounter</a>.


#### - NdisPDFreeCounter

See <a href="..\ndis\nc-ndis-ndis_pd_free_counter.md">NdisPDFreeCounter</a>.


#### - NdisPDQueryCounter

See <a href="..\ndis\nc-ndis-ndis_pd_query_counter.md">NdisPDQueryCounter</a>.


#### - NdisPDSetReceiveFilter

See <a href="..\ndis\nc-ndis-ndis_pd_set_receive_filter.md">NdisPDSetReceiveFilter</a>.


#### - NdisPDClearReceiveFilter

See <a href="..\ndis\nc-ndis-ndis_pd_clear_receive_filter.md">NdisPDClearReceiveFilter</a>.


### -field NdisPDRequestDrainNotification

 


### -field NdisPDQueueControl

 


### -field NdisPDProviderControl

 



#### - NdisPDOnRssReceiveQueues

See <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt808524(d=robot)">NdisPDOnRssReceiveQueues</a>.


#### - NdisPDOffRssReceiveQueues

See <a href="https://msdn.microsoft.com/library/windows/hardware/dn931860(d=robot)">NdisPDOffRssReceiveQueues</a>.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_PROVIDER_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

