---
UID: NF:ndis.NdisCmDispatchCallConnected
title: NdisCmDispatchCallConnected function (ndis.h)
description: NdisCmDispatchCallConnected notifies NDIS and the client that data transfers can begin on a VC that the call manager created for an incoming call initiated on a remote node.
old-location: netvista\ndiscmdispatchcallconnected.htm
tech.root: netvista
ms.assetid: c5fcca82-ab8f-4ea9-86df-295f43fe7afa
ms.date: 05/02/2018
keywords: ["NdisCmDispatchCallConnected function"]
ms.keywords: NdisCmDispatchCallConnected, NdisCmDispatchCallConnected function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_15a94b5d-378c-46f0-9808-411d1e92218c.xml, ndis/NdisCmDispatchCallConnected, netvista.ndiscmdispatchcallconnected
f1_keywords:
 - "ndis/NdisCmDispatchCallConnected"
 - "NdisCmDispatchCallConnected"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDispatchCallConnected   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDispatchCallConnected   (NDIS 5.1)) in Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCmDispatchCallConnected
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDispatchCallConnected function


## -description


<b>NdisCmDispatchCallConnected</b> notifies NDIS and the client that data transfers can begin on a VC that
  the call manager created for an 
  <i>incoming</i> call initiated on a remote node.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle to the VC that represents the connection, which was created with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> when the call manager's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
     ProtocolCoReceiveNetBufferLists</a> function was notified of the incoming call.


## -remarks



A stand-alone CM's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
    ProtocolCmIncomingCallComplete</a> function calls 
    <b>NdisCmDispatchCallConnected</b> to complete the final handshake for an incoming call from a remote
    node, which the client has already accepted.

A call to 
    <b>NdisCmDispatchCallConnected</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">
    ProtocolClCallConnected</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchCallConnected</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchCallConnected</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchcallconnected">NdisMCmDispatchCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">ProtocolClCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_incoming_call_complete">
   ProtocolCmIncomingCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>
 

 

