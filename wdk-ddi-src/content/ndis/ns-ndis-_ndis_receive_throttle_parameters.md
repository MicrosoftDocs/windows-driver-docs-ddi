---
UID: NS:ndis._NDIS_RECEIVE_THROTTLE_PARAMETERS
title: _NDIS_RECEIVE_THROTTLE_PARAMETERS
author: windows-driver-content
description: The NDIS_RECEIVE_THROTTLE_PARAMETERS structure specifies the maximum number of NET_BUFFER_LIST structures that a miniport driver should indicate in a deferred procedure call (DPC).
old-location: netvista\ndis_receive_throttle_parameters.htm
old-project: netvista
ms.assetid: ad51cc5c-7385-405b-8b65-20b079a3265c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_processor_group_ref_97a7b040-82a4-46ab-8b95-0f1be9823b8e.xml, NDIS_RECEIVE_THROTTLE_PARAMETERS, *PNDIS_RECEIVE_THROTTLE_PARAMETERS, PNDIS_RECEIVE_THROTTLE_PARAMETERS, netvista.ndis_receive_throttle_parameters, ndis/NDIS_RECEIVE_THROTTLE_PARAMETERS, NDIS_RECEIVE_THROTTLE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_THROTTLE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_THROTTLE_PARAMETERS, ndis/PNDIS_RECEIVE_THROTTLE_PARAMETERS
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
-	ndis.h
apiname: 
-	NDIS_RECEIVE_THROTTLE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: *PNDIS_RECEIVE_THROTTLE_PARAMETERS, NDIS_RECEIVE_THROTTLE_PARAMETERS
---

# _NDIS_RECEIVE_THROTTLE_PARAMETERS structure


## -description


The NDIS_RECEIVE_THROTTLE_PARAMETERS structure specifies the maximum number of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that a miniport
  driver should indicate in a deferred procedure call (DPC).


## -syntax


````
typedef struct _NDIS_RECEIVE_THROTTLE_PARAMETERS {
  ULONG MaxNblsToIndicate;
  ULONG MoreNblsPending  :1;
} NDIS_RECEIVE_THROTTLE_PARAMETERS, *PNDIS_RECEIVE_THROTTLE_PARAMETERS;
````


## -struct-fields




### -field MaxNblsToIndicate

The maximum number of 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that a miniport
     driver should include in a receive indication. If this value is NDIS_INDICATE_ALL_NBLS, the miniport can
     indicate all of the NET_BUFFER_LIST structures that it has.


### -field MoreNblsPending

A value that, when <b>TRUE</b>, specifies that the miniport driver has NET_BUFFER_LIST structures pending
     after it processed the maxim number or structures that NDIS requested in the 
     <b>MaxNblsToIndicate</b> member. 
     
<div class="alert"><b>Note</b>  If NDIS set the 
     <b>MaxNblsToIndicate</b> member to NDIS_INDICATE_ALL_NBLS, the miniport driver should set 
     <b>MoreNblsPending</b> to <b>FALSE</b> before it returns from the DPC.</div><div> </div>

## -remarks


The 
    <i>ReceiveThrottleParameters</i> parameters of the 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> and the 
    <mshelp:link keywords="netvista.miniportmessageinterruptdpc" tabindex="0"><i>
    MiniportMessageInterruptDPC</i></mshelp:link> DPC handler functions point to an NDIS_RECEIVE_THROTTLE_PARAMETERS
    structure. This structure specifies the parameters of 
    <mshelp:link keywords="netvista.receive_side_throttle_in_ndis_6_20" tabindex="0">Receive Side Throttle
    (RST)</mshelp:link> in NDIS 6.20 and later.

On entry to the DPC handler, the 
    <b>MaxNblsToIndicate</b> member of the NDIS_RECEIVE_THROTTLE_PARAMETERS structure specifies the maximum
    number of 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that the miniport
    driver should indicate in the DPC. If this value is NDIS_INDICATE_ALL_NBLS, the miniport driver can
    indicate all of the NET_BUFFER_LIST structures that it has in its queues.

After the miniport driver processes the specified maximum number of NET_BUFFER_LIST structures, the
    miniport driver might have more packets in its receive queues. In this case, the miniport driver should
    set the 
    <b>MoreNblsPending</b> member to <b>TRUE</b> and it should not re-enable interrupts before it returns from the
    DPC. This is true for both line-based and message biased interrupts.

The miniport driver should follow these guidelines when the 
    <b>MaxNblsToIndicate</b> member is set to NDIS_INDICATE_ALL_NBLS:
<ul>
<li>A value of NDIS_INDICATE_ALL_NBLS allows the miniport driver to determine the number of
     NET_BUFFER_LIST structures that it indicates in a DPC call. This gives the miniport driver the following
     options:
     <ul>
<li>The miniport driver can indicate all of its pending NET_BUFFER_LIST structures from its receive
      queues.</li>
<li>
The miniport driver can limit the number of NET_BUFFER_LIST structures that it indicates based on
       its heuristics to avoid spending an excessive amount of time within a DPC call.

In particular, the driver should use its heuristics to avoid a DPC timeout, which is the maximum
       amount of time the driver can spend in its DPC. When the timeout interval expires, a bugcheck occurs
       on the system. Starting with Windows 7, the DPC timeout is 10 seconds.

</li>
</ul>
</li>
<li>
The miniport driver should set 
      <b>MoreNblsPending</b> to <b>FALSE</b> before it returns from the DPC. The driver should do this regardless of
      whether it has pending NET_BUFFER_LIST structures in its receive queues that have not been
      indicated.

</li>
</ul>If the miniport driver is using line-based interrupts or a single MSI message, it should do
    interrupt-processing for all of the interrupt sources that it has. If there are packets in the receive
    queue, it should indicate at most 
    <b>MaxNblsToIndicate</b> NET_BUFFER_LIST structures to NDIS with the 
    <mshelp:link keywords="netvista.ndismindicatereceivenetbufferlists" tabindex="0"><b>
    NdisMIndicateReceiveNetBufferLists</b></mshelp:link> function.

If the miniport driver is using multiple MSI messages to differentiate different interrupt sources, it
    should ignore the 
    <i>ReceiveThrottleParameters</i> member for MSI messages that are not associated with receive indications.
    For receive interrupt messages, the miniport driver should indicate at most 
    <b>MaxNblsToIndicate</b> NET_BUFFER_LIST structures.
<div class="alert"><b>Note</b>  If the miniport driver sets 
    <b>MoreNblsPending</b>, NDIS will call the DPC again. However, the amount of time that passes before the
    next DPC call is not defined. Also, the amount of time between the initial interrupt service routing
    (ISR) returns and the DPC is not defined. After the miniport driver sets <b>MoreNblsPending</b>, it should handle the next DPC as it handled the first DPC.</div><div> </div>


## -see-also

<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>

<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>

<mshelp:link keywords="netvista.ndismindicatereceivenetbufferlists" tabindex="0"><b>
   NdisMIndicateReceiveNetBufferLists</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_THROTTLE_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

