---
UID: NS:ntddndis._NDIS_PD_CAPABILITIES
title: "_NDIS_PD_CAPABILITIES"
author: windows-driver-content
description: This structure indicates the PD capabilities for a provider.
old-location: netvista\ndis_pd_capabilities.htm
old-project: netvista
ms.assetid: A31D3F92-FB03-489B-894D-5E2F76AC3A99
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDIS_PD_CAPABILITIES, NDIS_PD_CAPABILITIES structure [Network Drivers Starting with Windows Vista], _NDIS_PD_CAPABILITIES, netvista.ndis_pd_capabilities, ntddndis/NDIS_PD_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_PD_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: NDIS_PD_CAPABILITIES
---

# _NDIS_PD_CAPABILITIES structure


## -description


This structure indicates the PD capabilities for a provider.


## -syntax


````
typedef struct _NDIS_PD_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              MaximumTxPartialBufferCount;
  ULONG              MaximumRxPartialBufferCount;
  UCHAR              RxFilterContextWidth;
  UCHAR              DmaAddressWidth;
  UCHAR              CapabilityFlags;
  ULONG              MaxNumberOfRxQueues;
  ULONG              MaxNumberOfTxQueues;
  ULONG              MaxNumberOfRxQueuesForDefaultVport;
  ULONG              MaxNumberOfTxQueuesForDefaultVport;
  ULONG              MaxNumberOfRxQueuesPerNonDefaultVport;
  ULONG              MaxNumberOfTxQueuesPerNonDefaultVport;
  ULONG              ExactMatchProfileArrayOffset;
  ULONG              ExactMatchProfileArrayNumElements;
  ULONG              ExactMatchProfileArrayElementSize;
  ULONG              WildcardMatchProfileArrayOffset;
  ULONG              WildcardMatchProfileArrayNumElements;
  ULONG              WildcardMatchProfileArrayElementSize;
} NDIS_PD_CAPABILITIES;
````


## -struct-fields




### -field Header

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_CAPABILITIES</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_CAPABILITIES_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_CAPABILITIES_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field MaximumTxPartialBufferCount

The maximum partial transmit <a href="..\ndis\ns-ndis-_pd_buffer.md">PD_BUFFER</a> chain lengths supported by the provider.


### -field MaximumRxPartialBufferCount

The maximum partial receive <a href="..\ndis\ns-ndis-_pd_buffer.md">PD_BUFFER</a> chain lengths supported by the provider.


### -field RxFilterContextWidth

The filter context width that the provider supports. A provider can support up to 64-bits in width.


### -field CapabilityFlags

Flags that contain additional capabilities that the provider supports.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>NDIS_PD_CAPS_RECEIVE_FILTER_COUNTERS_SUPPORTED</b></td>
<td>This flag indicates that the provider supports creation of counters with the <b>PDCounterTypeReceiveFilter</b> type that is part of the <a href="..\ndis\ne-ndis-ndis_pd_counter_type.md">NDIS_PD_COUNTER</a> enumeration</td>
</tr>
</table>
 


### -field MaxNumberOfRxQueues

The maximum number of receive queues the provider supports. This is only relevant to queues created by the  <a href="..\ndis\nc-ndis-ndis_pd_allocate_queue.md">NdisPDAllocateQueue</a> routine, therefore this number is not accurate for the client because additional pre-existing RSS queues (that the client can request PD-mode access to using the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt808524(d=robot)">NdisPDOnRssReceiveQueues</a>) are not accounted for in the <i>NdisPDAllocateQueue</i> routine.

It is possible for providers to set this value to 0, if it only supports clients to put pre-existing RSS queues into PD-mode using the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt808524(d=robot)">NdisPDOnRssReceiveQueues</a> routine.


### -field MaxNumberOfTxQueues

The maximum number of transmit queues the provider can create using the <a href="..\ndis\nc-ndis-ndis_pd_allocate_queue.md">NdisPDAllocateQueue</a> routine. The provider must not set this value to 0.


### -field MaxNumberOfRxQueuesForDefaultVport

The maximum number of receive queues that the provider supports for the default virtual port.


### -field MaxNumberOfTxQueuesForDefaultVport

The maximum number of transmit queues that the provider supports for the default virtual port.


### -field MaxNumberOfRxQueuesPerNonDefaultVport

The maximum number of receive queues that the provider supports for non-default virtual ports.


### -field MaxNumberOfTxQueuesPerNonDefaultVport

The maximum number of transmit queues that the provider supports for non-default virtual ports.


### -field ExactMatchProfileArrayOffset

The array offset for an array of NDIS_GFP_EXACT_MATCH_PROFILE structures.


### -field ExactMatchProfileArrayNumElements

The number of elements for an array of NDIS_GFP_EXACT_MATCH_PROFILE structures.


### -field ExactMatchProfileArrayElementSize

The number of elements for an array of NDIS_GFP_EXACT_MATCH_PROFILE structures.


### -field WildcardMatchProfileArrayOffset

The array offset for an array of NDIS_GFP_WILDCARD_MATCH_PROFILE structures.


### -field WildcardMatchProfileArrayNumElements

The number of elements for an array of NDIS_GFP_WILDCARD_MATCH_PROFILE structures.


### -field WildcardMatchProfileArrayElementSize

The number of elements for an array of NDIS_GFP_WILDCARD_MATCH_PROFILE structures.


### -field MinimumModerationInterval

 


### -field MaximumModerationInterval

 


### -field ModerationIntervalGranularity

 


### -field MaxRxQueueSize

 


### -field MaxTxQueueSize

 




#### - DmaAddressWidth

The DMA address width that the provider supports. Ideally, providers would support a 64-bit wide DMA address width, and setting this value to 0 indicates that a 64-bit wide DMA address. Providers must support a minimum of 32-bits in width, this means that valid values are either 0 or between 32-64 inclusive.


## -remarks



This structure must be aligned on an 8-byte boundary.

If the provider has a flexible implementation where it supports a maximum number of N queues, where any queue can be purposed flexibly as either an Rx or Tx queue, the provider should advertise ~N/2 for the MaxNumberOfRxQueues and MaxNumberOfTxQueues values because clients typically create a matching number of Rx and Tx queues. 

If a provider can partition Rx or Tx queues flexibly between virtual ports then is can use NDIS_PD_QUEUE_COUNT_DYNAMIC for the virtual port specific max counts.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_CAPABILITIES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

