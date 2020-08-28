---
UID: NF:ndis.NdisMCmDispatchIncomingCallQoSChange
title: NdisMCmDispatchIncomingCallQoSChange macro (ndis.h)
description: NdisMCmDispatchIncomingCallQoSChange notifies a client that a request to change the quality of service on that client's active connection has been received over the network.
old-location: netvista\ndismcmdispatchincomingcallqoschange.htm
tech.root: netvista
ms.assetid: e3da62c2-4940-4c55-8232-1780d92b7f1f
ms.date: 05/02/2018
keywords: ["NdisMCmDispatchIncomingCallQoSChange macro"]
ms.keywords: NdisMCmDispatchIncomingCallQoSChange, NdisMCmDispatchIncomingCallQoSChange macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_d926c691-a75e-4195-9026-67429043a821.xml, ndis/NdisMCmDispatchIncomingCallQoSChange, netvista.ndismcmdispatchincomingcallqoschange
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisMCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows XP.
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
 - NdisMCmDispatchIncomingCallQoSChange
 - ndis/NdisMCmDispatchIncomingCallQoSChange
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCmDispatchIncomingCallQoSChange
---

# NdisMCmDispatchIncomingCallQoSChange macro


## -description

<b>NdisMCmDispatchIncomingCallQoSChange</b> notifies a client that a request to change the quality of
  service on that client's active connection has been received over the network.

## -parameters

### -param _H_

Specifies the handle to the VC for which the change in QoS is being requested. The MCM driver
     obtained this handle either when it called 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> to set up this connection
     for an incoming call or as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param _P_

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that specifies the new
     QoS, requested by the client on the remote node, for this connection.

## -remarks

An MCM driver calls 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> to notify the client that it has received a request to modify
    the QoS on an active connection. Such an MCM driver supports dynamic QoS changes on active calls, which
    is a feature like QoS itself that depends on the signaling protocol.

The MCM driver should call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmactivatevc">NdisMCmActivateVc</a> whenever it makes
    changes in the call parameters for an active VC.

A call to 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingQoSChange</i> function. The client accepts the proposed modifications to the call
    parameters for the VC by doing nothing, except possibly updating any state it maintains about the QoS for
    the VC, and returning control. Otherwise, the client rejects the proposed QoS change by tearing down the
    call.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDispatchIncomingCallQoSChange</b>. Stand-alone call managers, which register themselves with
    NDIS as protocol drivers, call 
    <b>NdisCmDispatchIncomingCallQoSChange</b> instead.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcallqoschange">
   NdisCmDispatchIncomingCallQoSChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmactivatevc">NdisMCmActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call_qos_change">
   ProtocolClIncomingCallQosChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>

