---
UID: NF:ndis.NdisCmDispatchIncomingCall
title: NdisCmDispatchIncomingCall function
author: windows-driver-content
description: NdisCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client.
old-location: netvista\ndiscmdispatchincomingcall.htm
old-project: netvista
ms.assetid: 2172aeec-8502-414e-9d01-9292c0eb7ce8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisCmDispatchIncomingCall, NdisCmDispatchIncomingCall function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_892a99ac-d4f0-4f4b-9656-a43c99d67aca.xml, ndis/NdisCmDispatchIncomingCall, netvista.ndiscmdispatchincomingcall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDispatchIncomingCall   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDispatchIncomingCall   (NDIS 5.1)) in Windows XP.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCmDispatchIncomingCall
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmDispatchIncomingCall function


## -description


<b>NdisCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client.


## -parameters




### -param NdisSapHandle [in]

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>, and the call
     manager originally obtained this handle as an input parameter to its 
     <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">
     ProtocolCmRegisterSap</a> function.


### -param NdisVcHandle [in]

Specifies the handle identifying the VC, created with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a> when the call manager
     processes the incoming call offer directed to this registered SAP.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the
     traffic and media parameters for the VC.


## -returns



When 
     <b>NdisCmDispatchIncomingCall</b> returns anything other than NDIS_STATUS_PENDING, the call manager
     should make an internal call to its 
     <a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
     ProtocolCmIncomingCallComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmIncomingCallComplete</i> function when this operation is completed.




## -remarks



Before calling 
    <b>NdisCmDispatchIncomingCall</b>, a stand-alone call manager has already done the following:

<ul>
<li>
Identified the target SAP, previously registered by a particular client, for the call (actually, a
      request to make a connection) that it received over the network

</li>
<li>
Created a VC for the incoming call with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>


</li>
<li>
Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

</li>
<li>
Activated the VC with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a>, causing the
      underlying miniport driver to make itself ready for transfers on the VC in accord with the negotiated
      or accepted call parameters

</li>
</ul>
The CM's call to 
    <b>NdisCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a> function,
    within which the client either accepts or rejects the requested connection. After deciding whether to
    accept the connection, the client calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561632">NdisClIncomingCallComplete</a>,
    which, in turn, calls the CM's 
    <a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
    ProtocolCmIncomingCallComplete</a> function. If the client accepted the call, the CM next calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561661">NdisCmDispatchCallConnected</a>.
    Otherwise, it deactivates (and possibly deletes) the VC it created, after notifying the remote node that
    the offered call was rejected.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCall</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchIncomingCall</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561632">NdisClIncomingCallComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561661">NdisCmDispatchCallConnected</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561728">NdisCoSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562830">NdisMCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a>



<a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
   ProtocolCmIncomingCallComplete</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>



<a href="https://msdn.microsoft.com/1755804c-d82f-465d-862f-8a2340516f8e">
   ProtocolCoReceiveNetBufferLists</a>
 

 

