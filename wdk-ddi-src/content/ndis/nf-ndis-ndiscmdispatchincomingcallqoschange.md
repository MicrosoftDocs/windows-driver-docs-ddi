---
UID: NF:ndis.NdisCmDispatchIncomingCallQoSChange
title: NdisCmDispatchIncomingCallQoSChange function (ndis.h)
description: NdisCmDispatchIncomingCallQoSChange notifies a client that a request to change the quality of service on that client's active connection has been received over the network.
old-location: netvista\ndiscmdispatchincomingcallqoschange.htm
tech.root: netvista
ms.assetid: eee2625e-6dc8-4f54-81e9-2d31d25f62d7
ms.date: 05/02/2018
keywords: ["NdisCmDispatchIncomingCallQoSChange function"]
ms.keywords: NdisCmDispatchIncomingCallQoSChange, NdisCmDispatchIncomingCallQoSChange function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_01f18e60-ebc6-4192-9544-a57b07a4575e.xml, ndis/NdisCmDispatchIncomingCallQoSChange, netvista.ndiscmdispatchincomingcallqoschange
f1_keywords:
 - "ndis/NdisCmDispatchIncomingCallQoSChange"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows XP.
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
- NdisCmDispatchIncomingCallQoSChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDispatchIncomingCallQoSChange function


## -description


<b>NdisCmDispatchIncomingCallQoSChange</b> notifies a client that a request to change the quality of service
  on that client's active connection has been received over the network.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle to the VC for which the change in QoS is being requested. The call manager
     originally obtained this handle either when it called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> to set up this connection
     for an incoming call or as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that specifies the new
     QoS, requested by the client on the remote node, for this connection.


## -remarks



A stand-alone call manager calls 
    <b>NdisCmDispatchIncomingCallQoSChange</b> to notify the client that it has received a request to modify
    the QoS on an active connection. Such a CM supports dynamic QoS changes on active calls, which is a
    feature like QoS itself that depends on the signaling protocol.

When the CM itself receives a request for a QoS change, the call manager passes appropriately modified
    call parameters to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a>, so the underlying
    miniport driver also is notified of the proposed QoS change. Assuming the underlying miniport driver
    accepts the changed call parameters, the CM then calls 
    <b>NdisCmDispatchIncomingCallQoSChange</b>.

A call to 
    <b>NdisCmDispatchIncomingCallQoSChange</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingQoSChange</i> function. The client accepts the proposed modifications to the call
    parameters for the VC by doing nothing, except possibly updating any state it maintains about the QoS for
    the VC, and returning control. Otherwise, the client rejects the proposed QoS change by tearing down the
    call.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCallQoSChange</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> instead.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcallqoschange">
   NdisMCmDispatchIncomingCallQoSChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call_qos_change">
   ProtocolClIncomingCallQosChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_receive_net_buffer_lists">
   ProtocolCoReceiveNetBufferLists</a>
 

 

