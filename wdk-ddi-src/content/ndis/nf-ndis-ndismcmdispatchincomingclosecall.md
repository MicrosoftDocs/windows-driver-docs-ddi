---
UID: NF:ndis.NdisMCmDispatchIncomingCloseCall
title: NdisMCmDispatchIncomingCloseCall macro (ndis.h)
description: NdisMCmDispatchIncomingCloseCall tells a client to tear down an active or offered call, usually because the MCM driver has received a request from the network to close the connection.
old-location: netvista\ndismcmdispatchincomingclosecall.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCmDispatchIncomingCloseCall macro"]
ms.keywords: NdisMCmDispatchIncomingCloseCall, NdisMCmDispatchIncomingCloseCall macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_b5a94c5f-7483-44dd-8167-6e64f52cada6.xml, ndis/NdisMCmDispatchIncomingCloseCall, netvista.ndismcmdispatchincomingclosecall
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCmDispatchIncomingCloseCall
 - ndis/NdisMCmDispatchIncomingCloseCall
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCmDispatchIncomingCloseCall
---

# NdisMCmDispatchIncomingCloseCall macro


## -description

<b>NdisMCmDispatchIncomingCloseCall</b> tells a client to tear down an active or offered call, usually
  because the MCM driver has received a request from the network to close the connection.

## -parameters

### -param _S_

Specifies a caller-determined NDIS_STATUS_<i>XXX</i>, indicating the reason for the disconnect request. During normal network operations, an MCM
     driver passes NDIS_STATUS_SUCCESS to indicate that it has received a request, initiated by the remote
     party, to close an active call.

### -param _H_

Specifies the handle to the VC of the call being disconnected. This handle was supplied by NDIS
     when the VC was originally created, whether by the MCM driver with 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> or as an input parameter
     to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param _B_

Pointer to a caller-allocated resident buffer containing additional protocol-specific disconnect
     data, if any. Depending on the underlying medium, this pointer can be <b>NULL</b>.

### -param _Z_

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.

## -remarks

In the course of normal network operations, an MCM driver calls 
    <b>NdisMCmDispatchIncomingCloseCall</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because the corresponding client on the remote node has
    called 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

However, an MCM driver also can call 
    <b>NdisMCmDispatchIncomingCloseCall</b> if either of the following occur:

<ul>
<li>
The MCM driver has notified a client of an incoming call offer. When the miniport driver's 
      <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
      ProtocolCmIncomingCallComplete</a> function is called with the client's acceptance, it validates the
      input call parameters, which that client has modified. 
      <i>ProtocolCmIncomingCallComplete</i> determines that the client is proposing unsupportable call
      parameters for the connection, so it calls 
      <b>NdisMCmDispatchIncomingCloseCall</b>.

</li>
<li>
Abormal network conditions force the MCM driver to tear down active calls. For example, if the MCM
      driver is notified when any link on the connection between this client and the remote party to the
      connection goes down, the miniport driver would call 
      <b>NdisCmDispatchIncomingCloseCall</b> to prevent the client from attempting (or expecting) further data
      transfers on such a broken connection.

</li>
</ul>
After the client calls 
    <b>NdisClCloseCall</b> thereby causing the deactivation of the VC, the original creator of the VC is
    responsible for destroying the VC. Either the client calls 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>, which causes NDIS to call
    the MCM driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function, or the
    MCM driver calls 
    <b>NdisMCmDeleteVc</b> after calling 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a> and releasing any
    additional resources it had associated with the VC that it created.

A call to 
    <b>NdisMCmDispatchIncomingCloseCall</b> causes NDIS to call the client's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">
    ProtocolClIncomingCloseCall</a> function.

Only connection-oriented miniport drivers that provide call-management support can call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCloseCall</b> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingdropparty">
   NdisMCmDispatchIncomingDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
