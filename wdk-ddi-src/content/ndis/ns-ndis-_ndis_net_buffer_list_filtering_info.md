---
UID: NS:ndis._NDIS_NET_BUFFER_LIST_FILTERING_INFO
title: "_NDIS_NET_BUFFER_LIST_FILTERING_INFO"
author: windows-driver-content
description: The NDIS_NET_BUFFER_LIST_FILTERING_INFO structure defines filtering information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_net_buffer_list_filtering_info.htm
old-project: netvista
ms.assetid: 992a4c77-e22f-4123-81e8-86c8030accfa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_NET_BUFFER_LIST_FILTERING_INFO, ,, B, D, E, F, G, I, L, N, NDIS_NET_BUFFER_LIST_FILTERING_INFO, NDIS_NET_BUFFER_LIST_FILTERING_INFO structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_NET_BUFFER_LIST_FILTERING_INFO, PNDIS_NET_BUFFER_LIST_FILTERING_INFO structure pointer [Network Drivers Starting with Windows Vista], R, S, T, U, _, _NDIS_NET_BUFFER_LIST_FILTERING_INFO, ndis/NDIS_NET_BUFFER_LIST_FILTERING_INFO, ndis/PNDIS_NET_BUFFER_LIST_FILTERING_INFO, ndis_netbuf_macros_media_specific_ad9f53c1-d93a-4b73-9903-76aa54acd563.xml, netvista.ndis_net_buffer_list_filtering_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
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
-	NDIS_NET_BUFFER_LIST_FILTERING_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_NET_BUFFER_LIST_FILTERING_INFO, *PNDIS_NET_BUFFER_LIST_FILTERING_INFO
---

# _NDIS_NET_BUFFER_LIST_FILTERING_INFO structure


## -description


The <b>NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure defines filtering information that is associated
  with a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
typedef struct _NDIS_NET_BUFFER_LIST_FILTERING_INFO {
  union {
    struct {
      USHORT FilterId;
#if (NDIS_SUPPORT_NDIS630)
      union {
#endif 
        USHORT QueueId;
#if (NDIS_SUPPORT_NDIS630)
        USHORT VPortId;
      } QueueVPortInfo;
#endif 
    } FilteringInfo;
    PVOID Value;
  };
} NDIS_NET_BUFFER_LIST_FILTERING_INFO, *PNDIS_NET_BUFFER_LIST_FILTERING_INFO;
````


## -struct-fields




### -field FilteringInfo

A structure that contains the following members:


### -field FilteringInfo.FilterId

A USHORT value that contains a receive filter identifier. The receive filter identifier is an
       integer from one to the number of receive filters that the network adapter supports. 

<div class="alert"><b>Note</b>  Starting with NDIS 6.20, this member must be set to zero.</div>
<div> </div>

### -field FilteringInfo.QueueVPortInfo

A union that contains the following members:



##### QueueVPortInfo.QueueId

A USHORT value that contains an identifier for a virtual machine  queue (VMQ) receive queue. The queue identifier is an integer between zero
       and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the value of this member must always be set to NDIS_DEFAULT_RECEIVE_QUEUE_ID  by miniport drivers that support the SR-IOV interface.</div>
<div> </div>


##### QueueVPortInfo.VPortId

A USHORT value that contains the identifier for a virtual port (VPort). A value of DEFAULT_VPORT_ID specifies the default VPort on the NIC switch. 

The VPort with the specified VPortId value must have previously been created through a set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.

<div class="alert"><b>Note</b>  For the VMQ interface, this member must be set to NDIS_DEFAULT_VPORT_ID.</div>
<div> </div>

#### - Value

A PVOID type value that is in a union with the 
      <b>FilteringInfo</b> member. This member lets a driver access all the information in the
      <b>NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure as one PVOID value.


## -remarks



Starting with NDIS 6.20, miniport drivers  use the <b>NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure to specify receive
    filter information that accompanies the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are associated with a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

To access the <b>NDIS_NET_BUFFER_LIST_FILTERING_INFO</b> structure from the NET_BUFFER_LIST OOB data, an NDIS
    driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies
    the 
    <b>NetBufferListFilteringInfo</b>  information type.

To access the identifier values directly, use the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568406">
    NET_BUFFER_LIST_RECEIVE_FILTER_ID</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh439946">NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID</a>, or 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568407">
    NET_BUFFER_LIST_RECEIVE_QUEUE_ID</a> macros.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568407">
   NET_BUFFER_LIST_RECEIVE_QUEUE_ID</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439946">NET_BUFFER_LIST_RECEIVE_FILTER_VPORT_ID</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568406">
   NET_BUFFER_LIST_RECEIVE_FILTER_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NET_BUFFER_LIST_FILTERING_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

