---
UID: NF:ndis.NdisCmDispatchIncomingDropParty
title: NdisCmDispatchIncomingDropParty function (ndis.h)
description: NdisCmDispatchIncomingDropParty notifies a client that it should remove a particular party on a multipoint VC, usually because the call manager has received a request over the network to close an active multipoint connection.
old-location: netvista\ndiscmdispatchincomingdropparty.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisCmDispatchIncomingDropParty function"]
ms.keywords: NdisCmDispatchIncomingDropParty, NdisCmDispatchIncomingDropParty function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_6f7730c4-030a-45a6-b873-833bf8033ce7.xml, ndis/NdisCmDispatchIncomingDropParty, netvista.ndiscmdispatchincomingdropparty
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows XP.
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
 - NdisCmDispatchIncomingDropParty
 - ndis/NdisCmDispatchIncomingDropParty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisCmDispatchIncomingDropParty
---

# NdisCmDispatchIncomingDropParty function


## -description

<b>NdisCmDispatchIncomingDropParty</b> notifies a client that it should remove a particular party on a
  multipoint VC, usually because the call manager has received a request over the network to close an active
  multipoint connection.

## -parameters

### -param DropStatus [in]


Indicates the reason this party is being dropped, usually NDIS_STATUS_SUCCESS if the remote party
     simply requested that its connection be closed.

### -param NdisPartyHandle [in]


Specifies the handle that identifies the party to be dropped from the multipoint VC, which must
     have other parties that are still connected.

### -param Buffer [in, optional]


Pointer to a caller-allocated resident buffer containing additional protocol-specific data
     received from the remote party, if any. Depending on the underlying medium, this pointer can be
     <b>NULL</b>.

### -param Size [in]


Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.

## -remarks

In the course of normal network operations, a stand-alone call manager's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
    ProtocolCoReceiveNetBufferLists</a> function calls 
    <b>NdisCmDispatchIncomingDropParty</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because a remote client on a multipoint connection has
    called 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

However, a call manager also can call 
    <b>NdisCmDispatchIncomingDropParty</b> with a CM-determined 
    <i>CloseStatus</i> at the behest of the network itself if abnormal network conditions occur, such as the
    failure of a switch on the path between the local client and one or more client(s) on an established
    multipoint connection.

A call to 
    <b>NdisCmDispatchIncomingDropParty</b> causes NDIS to call the client's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_drop_party">
    ProtocolClIncomingDropParty</a> function.

If the 
    <i>NdisPartyHandle</i> identifies the last remaining party on the given VC, the CM calls 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingclosecall">
    NdisCmDispatchIncomingCloseCall</a>, rather than 
    <b>NdisCmDispatchIncomingDropParty</b>.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingDropParty</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchIncomingDropParty</b> instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingclosecall">
   NdisCmDispatchIncomingCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingdropparty">
   NdisMCmDispatchIncomingDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_drop_party">ProtocolClIncomingDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>
