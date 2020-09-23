---
UID: NE:fwpsk.FWPS_NET_BUFFER_LIST_EVENT_TYPE0_
title: FWPS_NET_BUFFER_LIST_EVENT_TYPE0_ (fwpsk.h)
description: The FWPS_NET_BUFFER_LIST_EVENT_TYPE0 enumeration type specifies the possible status events that can cause the callout driver's FWPS_NET_BUFFER_LIST_NOTIFY_FN0 function to be called.Note  FWPS_NET_BUFFER_LIST_EVENT_TYPE0 is a specific version of FWPS_NET_BUFFER_LIST_EVENT_TYPE. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_net_buffer_list_event_type0.htm
tech.root: netvista
ms.assetid: 14225920-2f51-4fef-9501-812e3aff8905
ms.date: 05/02/2018
keywords: ["FWPS_NET_BUFFER_LIST_EVENT_TYPE0_ enumeration"]
ms.keywords: FWPS_NET_BUFFER_LIST_CLONED_BY_NDIS, FWPS_NET_BUFFER_LIST_CLONED_BY_NETIO, FWPS_NET_BUFFER_LIST_CLONED_VIA_WFP_API, FWPS_NET_BUFFER_LIST_CONTEXT_REMOVED, FWPS_NET_BUFFER_LIST_DUPLICATED_BY_NETIO, FWPS_NET_BUFFER_LIST_ENTERED_NETIO, FWPS_NET_BUFFER_LIST_EVENT_TYPE0, FWPS_NET_BUFFER_LIST_EVENT_TYPE0 enumeration [Network Drivers Starting with Windows Vista], FWPS_NET_BUFFER_LIST_EVENT_TYPE0_, FWPS_NET_BUFFER_LIST_EXIT_NETIO, FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_NATIVE_RECV_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_NATIVE_SEND_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE, FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETEFWPS_NET_BUFFER_LIST_CLONED_BY_NDIS, FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_INGRESS_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_CLONED_BY_NDIS, fwpsk/FWPS_NET_BUFFER_LIST_CLONED_BY_NETIO, fwpsk/FWPS_NET_BUFFER_LIST_CLONED_VIA_WFP_API, fwpsk/FWPS_NET_BUFFER_LIST_CONTEXT_REMOVED, fwpsk/FWPS_NET_BUFFER_LIST_DUPLICATED_BY_NETIO, fwpsk/FWPS_NET_BUFFER_LIST_ENTERED_NETIO, fwpsk/FWPS_NET_BUFFER_LIST_EVENT_TYPE0, fwpsk/FWPS_NET_BUFFER_LIST_EXIT_NETIO, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_NATIVE_RECV_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_NATIVE_SEND_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETEFWPS_NET_BUFFER_LIST_CLONED_BY_NDIS, fwpsk/FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_INGRESS_COMPLETE, netvista.fwps_net_buffer_list_event_type0, wfp_ref_4_enum_efc9d72c-0710-440a-8074-77ce1dffd9bf.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise indicated, supported starting with Windows Vista.
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
req.irql: 
targetos: Windows
req.typenames: FWPS_NET_BUFFER_LIST_EVENT_TYPE0
f1_keywords:
 - FWPS_NET_BUFFER_LIST_EVENT_TYPE0_
 - fwpsk/FWPS_NET_BUFFER_LIST_EVENT_TYPE0_
 - FWPS_NET_BUFFER_LIST_EVENT_TYPE0
 - fwpsk/FWPS_NET_BUFFER_LIST_EVENT_TYPE0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_NET_BUFFER_LIST_EVENT_TYPE0
---

# FWPS_NET_BUFFER_LIST_EVENT_TYPE0_ enumeration


## -description

The <b>FWPS_NET_BUFFER_LIST_EVENT_TYPE0</b> enumeration type specifies the possible status events that can
 cause the callout driver's 
 <a href="/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">
 FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> function to be called.
<div class="alert"><b>Note</b>  <b>FWPS_NET_BUFFER_LIST_EVENT_TYPE0</b> is a specific version of <b>FWPS_NET_BUFFER_LIST_EVENT_TYPE</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -enum-fields

### -field FWPS_NET_BUFFER_LIST_ENTERED_NETIO

The <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure entered the TCP/IP stack. Packets enter the stack either from
 the NDIS layer or as a result of a call to a WFP packet injection function.

### -field FWPS_NET_BUFFER_LIST_CLONED_BY_NETIO

The NET_BUFFER_LIST structure was cloned.

### -field FWPS_NET_BUFFER_LIST_CLONED_VIA_WFP_API

The NET_BUFFER_LIST structure was cloned by a call to the 
 <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">FwpsAllocateCloneNetBufferList0</a> function.

### -field FWPS_NET_BUFFER_LIST_DUPLICATED_BY_NETIO

The NET_BUFFER_LIST structure was duplicated.

### -field FWPS_NET_BUFFER_LIST_EXIT_NETIO

The NET_BUFFER_LIST structure is about to leave the TCP/IP stack.

### -field FWPS_NET_BUFFER_LIST_CONTEXT_REMOVED

The NET_BUFFER_LIST structure is outside of the context for which it was tagged. The
 circumstances for this event depend upon the specifics of the tagged packets.
 

<table>
<tr>
<th>Packet Type</th>
<th>Event Condition</th>
</tr>
<tr>
<td>
Outbound

</td>
<td>
The NET_BUFFER_LIST structure exits the TCP/IP stack.

</td>
</tr>
<tr>
<td>
Any

</td>
<td>
Upon asynchronous context removal resulting from a call to the 
 <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistremovecontext0">
 FwpsNetBufferListRemoveContext0</a> function.

</td>
</tr>
</table>

### -field FWPS_NET_BUFFER_LIST_NDIS_SEND_COMPLETE

See FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE.

### -field FWPS_NET_BUFFER_LIST_NDIS_RECV_COMPLETE

See FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE.

### -field FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_SEND_COMPLETE

The NET_BUFFER_LIST structure send over the upper (protocol driver) NDIS 802.3 layer is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_ETHERNET_RECV_COMPLETE

The NET_BUFFER_LIST structure receive over the upper (protocol driver) NDIS 802.3 layer is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_NATIVE_SEND_COMPLETE

The NET_BUFFER_LIST structure send over the lower (miniport driver) NDIS native layer is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_NATIVE_RECV_COMPLETE

The NET_BUFFER_LIST structure receive over the lower (miniport driver) NDIS native layer is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_INGRESS_COMPLETE

The NET_BUFFER_LIST structure ingress on the virtual switch is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETE

The NET_BUFFER_LIST structure egress on the virtual switch is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_CLONED_BY_NDIS

NDIS cloned the NET_BUFFER_LIST structure.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_REASSEMBLED_FRAGMENT

The NET_BUFFER_LIST structure is a reassembled fragment.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.1.</div>
<div> </div>

### -field FWPS_NET_BUFFER_LIST_REASSEMBLY_COMPLETE

The NET_BUFFER_LIST fragment reassembly is complete. 

<div class="alert"><b>Note</b>  Supported starting with Windows 8.1.</div>
<div> </div>

#### - FWPS_NET_BUFFER_LIST_NDIS_VSWITCH_EGRESS_COMPLETEFWPS_NET_BUFFER_LIST_CLONED_BY_NDIS

The NET_BUFFER_LIST structure egress on the virtual switch is complete.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">
 FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
 FwpsAllocateCloneNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistremovecontext0">
 FwpsNetBufferListRemoveContext0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>