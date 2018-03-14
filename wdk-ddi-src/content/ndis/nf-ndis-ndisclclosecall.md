---
UID: NF:ndis.NdisClCloseCall
title: NdisClCloseCall function
author: windows-driver-content
description: NdisClCloseCall requests that a call on the specified VC be torn down.
old-location: netvista\ndisclclosecall.htm
old-project: netvista
ms.assetid: 4d1a7451-8c0f-4df8-85c5-14aaaa9afd94
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisClCloseCall, NdisClCloseCall function [Network Drivers Starting with Windows Vista], condis_client_ref_6d047338-0482-4d26-8dfa-4c07502fb8a2.xml, ndis/NdisClCloseCall, netvista.ndisclclosecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClCloseCall (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClCloseCall (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisClCloseCall
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisClCloseCall function


## -description


<b>NdisClCloseCall</b> requests that a call on the specified VC be torn down.


## -syntax


````
NDIS_STATUS NdisClCloseCall(
  _In_     NDIS_HANDLE NdisVcHandle,
  _In_opt_ NDIS_HANDLE NdisPartyHandle,
  _In_opt_ PVOID       Buffer,
  _In_     UINT        Size
);
````


## -parameters




### -param NdisVcHandle [in]

Handle to the VC of the call being closed or disconnected. This handle was supplied by NDIS when
     the VC was originally created with 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>, whether by the client in
     preparation for making an outgoing call or by the call manager in preparation for dispatching an
     incoming call to the client.


### -param NdisPartyHandle [in, optional]

Handle to the last party to be dropped on a multipoint VC or <b>NULL</b>. If this is a multipoint VC, the
     client obtained this handle either from a preceding call to 
     <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> or 
     <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>.


### -param Buffer [in, optional]

Pointer to a caller-allocated buffer containing any data to be transmitted to the party on the
     remote node when the connection is closed. Depending on the underlying medium, this pointer can be
     <b>NULL</b>.


### -param Size [in]

Specifies the size, in bytes, at 
     <i>Buffer</i>, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## -returns



When 
     <b>NdisClCloseCall</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">
     ProtocolClCloseCallComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClCloseCallComplete</i> function when this operation is completed.




## -remarks



Clients usually call 
    <b>NdisClCloseCall</b> in any one of the following circumstances:

<ul>
<li>
To close an established call, whether the call was initiated by the client with 
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> or was offered by a remote
      peer and accepted by the client's 
      <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
      ProtocolClIncomingCall</a> function.

</li>
<li>
From the 
      <a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">
      ProtocolClIncomingCloseCall</a> function to tear down an established call.

This occurs when the remote party closes an incoming call that the remote party originally initiated
      and that the client accepted. For client-initiated outgoing calls, this occurs either when the remote
      party closes the point-to-point connection on the remote node or when the last remaining party on a
      multipoint VC closes the call on the remote node.

</li>
<li>
From the 
      <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">
      ProtocolClMakeCallComplete</a> function to tear down a client-initiated attempt to make an outgoing
      call.

This occurs if the call manager has modified the client-specified call parameters passed to 
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> and the client finds these
      modifications unacceptable.

</li>
<li>
From the 
      <i>ProtocolClIncomingQoSChange</i> function to tear down an established call.

This occurs if a QoS change proposed by the other party on the VC is unacceptable to the client.

</li>
<li>
From the 
      <a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
      ProtocolClModifyCallQoSComplete</a> function to tear down an established call.

This occurs if a client-proposed QoS change on the VC is not accepted and the CM-modified QoS
      returned to 
      <i>ProtocolClModifyCallQoSComplete</i> is unacceptable to the client.

</li>
</ul>
Before calling 
    <b>NdisClCloseCall</b>, a protocol must ensure that all its outstanding send packets have been returned
    to its 
    <a href="..\ndis\nc-ndis-protocol_co_send_net_buffer_lists_complete.md">
    ProtocolCoSendNetBufferListsComplete</a> function. (Packets sent via 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a> are
    always returned asynchronously to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.) After calling 
    <b>NdisClCloseCall</b>, a protocol must not call 
    <b>NdisCoSendNetBufferLists</b> to send
    packets on the VC referenced by 
    <b>NdisClCloseCall</b>.

A client's call to 
    <b>NdisClCloseCall</b> causes NDIS to mark the 
    <i>NdisVcHandle</i> as closing and to call the CM's 
    <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a> function.

To tear down an established call on a client-created multipoint VC, the client must call 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a> one or more times to
    release all but the last party on the VC 
    before it calls 
    <b>NdisClCloseCall</b>. The call manager will fail any client's request to close a multipoint call if the
    given VC still has more than one party connected. The 
    <i>NdisPartyHandle</i> passed to 
    <b>NdisClCloseCall</b> can be any valid handle that the client obtained from its preceding calls to 
    <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> or 
    <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> with the given 
    <i>NdisVcHandle</i> .

As remote parties to a client-initiated multipoint call request that their connections be closed, NDIS
    calls that client's 
    <i>ProtocolClDropParty</i> function as long as more than one outstanding party exists on the
    client-created multipoint VC. When the last remaining remote party closes its connection, NDIS calls the
    client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">
    ProtocolClIncomingCloseCall</a> function instead. Consequently, the 
    <i>ProtocolClIncomingCloseCall</i> function of any client that sets up multipoint connections must
    identify the last remaining party on its multipoint VCs and pass the appropriate 
    <i>NdisPartyHandle</i> to 
    <b>NdisClCloseCall</b>.

After the client releases an 
    <i>NdisPartyHandle</i> with 
    <b>NdisClCloseCall</b>, it can release (or reinitialize for reuse) the resources for the per-party state
    it was maintaining. However, the client cannot release or reuse its per-VC resources in a similar manner
    on completion of the operation it initiated with 
    <b>NdisClCloseCall</b> because the 
    <i>NdisVcHandle</i>, which cannot be reused to make another call because it is marked as closing, is
    still valid until the VC is destroyed. Either the client must call 
    <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a> if it created the VC for an
    outgoing call before it releases or reinitializes its per-VC resources, or the client must defer the
    release or reinitialization of these resources until its 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function is
    called.




## -see-also

<a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">ProtocolClCloseCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
   ProtocolClModifyCallQoSComplete</a>



<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">ProtocolClIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">ProtocolClIncomingCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_co_send_net_buffer_lists_complete.md">
   ProtocolCoSendNetBufferListsComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call_qos_change.md">
   ProtocolClIncomingCallQoSChange</a>



<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>



<a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">ProtocolClMakeCallComplete</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClCloseCall function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

