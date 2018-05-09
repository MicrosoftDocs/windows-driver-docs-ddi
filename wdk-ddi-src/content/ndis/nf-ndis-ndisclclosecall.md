---
UID: NF:ndis.NdisClCloseCall
title: NdisClCloseCall function
author: windows-driver-content
description: NdisClCloseCall requests that a call on the specified VC be torn down.
old-location: netvista\ndisclclosecall.htm
old-project: netvista
ms.assetid: 4d1a7451-8c0f-4df8-85c5-14aaaa9afd94
ms.author: windowsdriverdev
ms.date: 4/25/2018
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClCloseCall function


## -description


<b>NdisClCloseCall</b> requests that a call on the specified VC be torn down.


## -parameters




### -param NdisVcHandle [in]

Handle to the VC of the call being closed or disconnected. This handle was supplied by NDIS when
     the VC was originally created with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>, whether by the client in
     preparation for making an outgoing call or by the call manager in preparation for dispatching an
     incoming call to the client.


### -param NdisPartyHandle [in, optional]

Handle to the last party to be dropped on a multipoint VC or <b>NULL</b>. If this is a multipoint VC, the
     client obtained this handle either from a preceding call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a>.


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
     <a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">
     ProtocolClCloseCallComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClCloseCallComplete</i> function when this operation is completed.




## -remarks



Clients usually call 
    <b>NdisClCloseCall</b> in any one of the following circumstances:

<ul>
<li>
To close an established call, whether the call was initiated by the client with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a> or was offered by a remote
      peer and accepted by the client's 
      <a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">
      ProtocolClIncomingCall</a> function.

</li>
<li>
From the 
      <a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">
      ProtocolClIncomingCloseCall</a> function to tear down an established call.

This occurs when the remote party closes an incoming call that the remote party originally initiated
      and that the client accepted. For client-initiated outgoing calls, this occurs either when the remote
      party closes the point-to-point connection on the remote node or when the last remaining party on a
      multipoint VC closes the call on the remote node.

</li>
<li>
From the 
      <a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">
      ProtocolClMakeCallComplete</a> function to tear down a client-initiated attempt to make an outgoing
      call.

This occurs if the call manager has modified the client-specified call parameters passed to 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a> and the client finds these
      modifications unacceptable.

</li>
<li>
From the 
      <i>ProtocolClIncomingQoSChange</i> function to tear down an established call.

This occurs if a QoS change proposed by the other party on the VC is unacceptable to the client.

</li>
<li>
From the 
      <a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
      ProtocolClModifyCallQoSComplete</a> function to tear down an established call.

This occurs if a client-proposed QoS change on the VC is not accepted and the CM-modified QoS
      returned to 
      <i>ProtocolClModifyCallQoSComplete</i> is unacceptable to the client.

</li>
</ul>
Before calling 
    <b>NdisClCloseCall</b>, a protocol must ensure that all its outstanding send packets have been returned
    to its 
    <a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
    ProtocolCoSendNetBufferListsComplete</a> function. (Packets sent via 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561728">NdisCoSendNetBufferLists</a> are
    always returned asynchronously to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.) After calling 
    <b>NdisClCloseCall</b>, a protocol must not call 
    <b>NdisCoSendNetBufferLists</b> to send
    packets on the VC referenced by 
    <b>NdisClCloseCall</b>.

A client's call to 
    <b>NdisClCloseCall</b> causes NDIS to mark the 
    <i>NdisVcHandle</i> as closing and to call the CM's 
    <a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a> function.

To tear down an established call on a client-created multipoint VC, the client must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a> one or more times to
    release all but the last party on the VC 
    before it calls 
    <b>NdisClCloseCall</b>. The call manager will fail any client's request to close a multipoint call if the
    given VC still has more than one party connected. The 
    <i>NdisPartyHandle</i> passed to 
    <b>NdisClCloseCall</b> can be any valid handle that the client obtained from its preceding calls to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a> with the given 
    <i>NdisVcHandle</i> .

As remote parties to a client-initiated multipoint call request that their connections be closed, NDIS
    calls that client's 
    <i>ProtocolClDropParty</i> function as long as more than one outstanding party exists on the
    client-created multipoint VC. When the last remaining remote party closes its connection, NDIS calls the
    client's 
    <a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a> if it created the VC for an
    outgoing call before it releases or reinitializes its per-VC resources, or the client must defer the
    release or reinitialization of these resources until its 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function is
    called.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561636">NdisClModifyCallQoS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561728">NdisCoSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">ProtocolClCloseCallComplete</a>



<a href="https://msdn.microsoft.com/ca9953f4-35db-4acb-b0ea-887156b4f6ee">
   ProtocolClIncomingCallQoSChange</a>



<a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">ProtocolClIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/3815ca4b-f4bc-4de9-a28a-5d3ee20bcdd8">ProtocolClIncomingDropParty</a>



<a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">ProtocolClMakeCallComplete</a>



<a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
   ProtocolClModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a>



<a href="https://msdn.microsoft.com/fb4b00c0-0b14-48dd-a6f2-aae659c6bb28">
   ProtocolCoSendNetBufferListsComplete</a>
 

 

