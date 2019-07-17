---
UID: NF:ndis.NdisMCmDispatchIncomingDropParty
title: NdisMCmDispatchIncomingDropParty macro (ndis.h)
description: NdisMCmDispatchIncomingDropParty notifies a client that it should remove a particular party on a multipoint VC.
old-location: netvista\ndismcmdispatchincomingdropparty.htm
tech.root: netvista
ms.assetid: 4549b6f4-5138-4724-959c-a36b38c319fd
ms.date: 05/02/2018
ms.keywords: NdisMCmDispatchIncomingDropParty, NdisMCmDispatchIncomingDropParty macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_1a170d75-7913-4068-b047-206b531d42c6.xml, ndis/NdisMCmDispatchIncomingDropParty, netvista.ndismcmdispatchincomingdropparty
ms.topic: macro
f1_keywords:
 - "ndis/NdisMCmDispatchIncomingDropParty"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmDispatchIncomingDropParty (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisMCmDispatchIncomingDropParty (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmDispatchIncomingDropParty
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDispatchIncomingDropParty macro


## -description


<b>NdisMCmDispatchIncomingDropParty</b> notifies a client that it should remove a particular party on a
  multipoint VC.


## -parameters




### -param _S_

Indicates the reason this party is being dropped, usually NDIS_STATUS_SUCCESS if the remote party
     simply requested that its connection be closed.

### -param _H_

Specifies the handle that identifies the party to be dropped from the multipoint VC, which must
     have other parties that are still connected. The MCM driver originally obtained this handle as an input
     parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.

### -param _B_

Pointer to a caller-allocated resident buffer containing additional protocol-specific data
     received from the remote party, if any. Depending on the underlying medium, this pointer can be
     <b>NULL</b>.

### -param _Z_

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.
     
## -remarks



In the course of normal network operations, an MCM driver calls 
    <b>NdisMCmDispatchIncomingDropParty</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because a remote client on a multipoint connection has
    called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

However, an MCM driver also can call 
    <b>NdisMCmDispatchIncomingDropParty</b> with a driver-determined 
    <i>CloseStatus</i> at the behest of the network itself if abnormal network conditions occur, such as the
    failure of a switch on the path between the local client and one or more client(s) on an established
    multipoint connection.

A call to 
    <b>NdisMCmDispatchIncomingDropParty</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_incoming_drop_party">
    ProtocolClIncomingDropParty</a> function.

If the 
    <i>NdisPartyHandle</i> identifies the last remaining party on the given VC, the MCM driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdispatchincomingclosecall">
    NdisMCmDispatchIncomingCloseCall</a>, rather than 
    <b>NdisMCmDispatchIncomingDropParty</b>.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDispatchIncomingDropParty</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmDispatchIncomingDropParty</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmdispatchincomingdropparty">
   NdisCmDispatchIncomingDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdispatchincomingclosecall">
   NdisMCmDispatchIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_incoming_drop_party">ProtocolClIncomingDropParty</a>
 

 

