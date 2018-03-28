---
UID: NF:ndis.NdisMCmDispatchIncomingCallQoSChange
title: NdisMCmDispatchIncomingCallQoSChange macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCallQoSChange notifies a client that a request to change the quality of service on that client's active connection has been received over the network.
old-location: netvista\ndismcmdispatchincomingcallqoschange.htm
old-project: netvista
ms.assetid: e3da62c2-4940-4c55-8232-1780d92b7f1f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmDispatchIncomingCallQoSChange, NdisMCmDispatchIncomingCallQoSChange macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_d926c691-a75e-4195-9026-67429043a821.xml, ndis/NdisMCmDispatchIncomingCallQoSChange, netvista.ndismcmdispatchincomingcallqoschange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmDispatchIncomingCallQoSChange
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDispatchIncomingCallQoSChange macro


## -description


<b>NdisMCmDispatchIncomingCallQoSChange</b> notifies a client that a request to change the quality of
  service on that client's active connection has been received over the network.


## -parameters




### -param _H_

TBD


### -param _P_

TBD






#### - NdisVcHandle [in]

Specifies the handle to the VC for which the change in QoS is being requested. The MCM driver
     obtained this handle either when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a> to set up this connection
     for an incoming call or as an input parameter to its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the new
     QoS, requested by the client on the remote node, for this connection.


## -remarks



An MCM driver calls 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> to notify the client that it has received a request to modify
    the QoS on an active connection. Such an MCM driver supports dynamic QoS changes on active calls, which
    is a feature like QoS itself that depends on the signaling protocol.

The MCM driver should call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a> whenever it makes
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561636">NdisClModifyCallQoS</a>



<a href="https://msdn.microsoft.com/eee2625e-6dc8-4f54-81e9-2d31d25f62d7">
   NdisCmDispatchIncomingCallQoSChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>



<a href="https://msdn.microsoft.com/ca9953f4-35db-4acb-b0ea-887156b4f6ee">
   ProtocolClIncomingCallQosChange</a>



<a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDispatchIncomingCallQoSChange macro%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

