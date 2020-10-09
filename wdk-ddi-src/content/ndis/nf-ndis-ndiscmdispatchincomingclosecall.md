---
UID: NF:ndis.NdisCmDispatchIncomingCloseCall
title: NdisCmDispatchIncomingCloseCall function (ndis.h)
description: NdisCmDispatchIncomingCloseCall tells a client to tear down an active or offered call, usually because the call manager has received a request from the network to close the connection.
old-location: netvista\ndiscmdispatchincomingclosecall.htm
tech.root: netvista
ms.assetid: f0f1221d-3d95-4d4c-acd0-6bcd653241c4
ms.date: 05/02/2018
keywords: ["NdisCmDispatchIncomingCloseCall function"]
ms.keywords: NdisCmDispatchIncomingCloseCall, NdisCmDispatchIncomingCloseCall function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_877248ee-cc60-430c-836c-d2580627363f.xml, ndis/NdisCmDispatchIncomingCloseCall, netvista.ndiscmdispatchincomingclosecall
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisCmDispatchIncomingCloseCall
 - ndis/NdisCmDispatchIncomingCloseCall
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisCmDispatchIncomingCloseCall
---

# NdisCmDispatchIncomingCloseCall function


## -description

<b>NdisCmDispatchIncomingCloseCall</b> tells a client to tear down an active or offered call, usually
  because the call manager has received a request from the network to close the connection.

## -parameters

### -param CloseStatus 

[in]
Specifies a CM-determined NDIS_STATUS_<i>XXX</i>, indicating the reason for the disconnect request. During normal network operations, a call
     manager passes NDIS_STATUS_SUCCESS to indicate that it has received a request, initiated by the remote
     party, to close an active call.

### -param NdisVcHandle 

[in]
Specifies the handle to the VC of the call being disconnected. This handle was supplied by NDIS
     when the VC was originally created, whether by the call manager or client, with 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>.

### -param Buffer 

[in, optional]
Pointer to a caller-allocated resident buffer containing additional protocol-specific disconnect
     data, if any. Depending on the underlying medium, this pointer can be <b>NULL</b>

### -param Size 

[in]
Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.

## -remarks

In the course of normal network operations, a stand-alone CM calls 
    <b>NdisCmDispatchIncomingCloseCall</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because the corresponding client on the remote node has
    called 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

However, a call manager also can call 
    <b>NdisCmDispatchIncomingCloseCall</b> if either of the following occurs:

<ul>
<li>
The call manager has notified a client of an incoming call offer. When the CM's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
      ProtocolCmIncomingCallComplete</a> function is called with the client's acceptance, it validates the
      input call parameters, which that client has modified. 
      <i>ProtocolCmIncomingCallComplete</i> determines that the client is proposing unsupportable call
      parameters for the connection, so it calls 
      <b>NdisCmDispatchIncomingCloseCall</b>.

</li>
<li>
Abormal network conditions force the call manager to tear down active calls. For example, if the
      call manager is notified when any link on the connection between this client and the remote party to
      the connection goes down, the CM would call 
      <b>NdisCmDispatchIncomingCloseCall</b> to prevent the client from attempting (or expecting) further data
      transfers on such a broken connection.

</li>
</ul>
After tearing down any call, the original creator of the VC is responsible for calling 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a> after releasing any
    additional resources it had associated with the VC.

A call to 
    <b>NdisCmDispatchIncomingCloseCall</b> causes NDIS to call the client's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">
    ProtocolClIncomingCloseCall</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCloseCall</b>. Connection-oriented miniport drivers that provide call-management
    support call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">
    NdisMCmDispatchIncomingCall</a> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingdropparty">
   NdisCmDispatchIncomingDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingclosecall">
   NdisMCmDispatchIncomingCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_status_ex">ProtocolCoStatusEx</a>