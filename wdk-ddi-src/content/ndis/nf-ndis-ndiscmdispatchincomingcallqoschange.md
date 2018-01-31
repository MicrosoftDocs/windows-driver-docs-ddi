---
UID: NF:ndis.NdisCmDispatchIncomingCallQoSChange
title: NdisCmDispatchIncomingCallQoSChange function
author: windows-driver-content
description: NdisCmDispatchIncomingCallQoSChange notifies a client that a request to change the quality of service on that client's active connection has been received over the network.
old-location: netvista\ndiscmdispatchincomingcallqoschange.htm
old-project: netvista
ms.assetid: eee2625e-6dc8-4f54-81e9-2d31d25f62d7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: condis_call_manager_ref_01f18e60-ebc6-4192-9544-a57b07a4575e.xml, ndis/NdisCmDispatchIncomingCallQoSChange, netvista.ndiscmdispatchincomingcallqoschange, NdisCmDispatchIncomingCallQoSChange, NdisCmDispatchIncomingCallQoSChange function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCmDispatchIncomingCallQoSChange
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmDispatchIncomingCallQoSChange function


## -description


<b>NdisCmDispatchIncomingCallQoSChange</b> notifies a client that a request to change the quality of service
  on that client's active connection has been received over the network.


## -syntax


````
VOID NdisCmDispatchIncomingCallQoSChange(
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




#### - NdisVcHandle [in]

Specifies the handle to the VC for which the change in QoS is being requested. The call manager
     originally obtained this handle either when it called 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> to set up this connection
     for an incoming call or as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the new
     QoS, requested by the client on the remote node, for this connection.


## -returns


None



## -remarks


A stand-alone call manager calls 
    <b>NdisCmDispatchIncomingCallQoSChange</b> to notify the client that it has received a request to modify
    the QoS on an active connection. Such a CM supports dynamic QoS changes on active calls, which is a
    feature like QoS itself that depends on the signaling protocol.

When the CM itself receives a request for a QoS change, the call manager passes appropriately modified
    call parameters to 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>, so the underlying
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

<mshelp:link keywords="netvista.ndismcmdispatchincomingcallqoschange" tabindex="0"><b>
   NdisMCmDispatchIncomingCallQoSChange</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>

<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>

<mshelp:link keywords="netvista.protocolcoreceivenetbufferlists" tabindex="0"><i>
   ProtocolCoReceiveNetBufferLists</i></mshelp:link>

<mshelp:link keywords="netvista.protocolclincomingcallqoschange" tabindex="0"><i>
   ProtocolClIncomingCallQosChange</i></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>

<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>

<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmDispatchIncomingCallQoSChange function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

