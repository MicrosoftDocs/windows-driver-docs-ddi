---
UID: NF:ndis.NdisCmDispatchIncomingCloseCall
title: NdisCmDispatchIncomingCloseCall function
author: windows-driver-content
description: NdisCmDispatchIncomingCloseCall tells a client to tear down an active or offered call, usually because the call manager has received a request from the network to close the connection.
old-location: netvista\ndiscmdispatchincomingclosecall.htm
tech.root: netvista
ms.assetid: f0f1221d-3d95-4d4c-acd0-6bcd653241c4
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisCmDispatchIncomingCloseCall, NdisCmDispatchIncomingCloseCall function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_877248ee-cc60-430c-836c-d2580627363f.xml, ndis/NdisCmDispatchIncomingCloseCall, netvista.ndiscmdispatchincomingclosecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.
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
-	NdisCmDispatchIncomingCloseCall
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDispatchIncomingCloseCall function


## -description


<b>NdisCmDispatchIncomingCloseCall</b> tells a client to tear down an active or offered call, usually
  because the call manager has received a request from the network to close the connection.


## -parameters




### -param CloseStatus [in]

Specifies a CM-determined NDIS_STATUS_<i>XXX</i>, indicating the reason for the disconnect request. During normal network operations, a call
     manager passes NDIS_STATUS_SUCCESS to indicate that it has received a request, initiated by the remote
     party, to close an active call.


### -param NdisVcHandle [in]

Specifies the handle to the VC of the call being disconnected. This handle was supplied by NDIS
     when the VC was originally created, whether by the call manager or client, with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>.


### -param Buffer [in, optional]

Pointer to a caller-allocated resident buffer containing additional protocol-specific disconnect
     data, if any. Depending on the underlying medium, this pointer can be <b>NULL</b>


### -param Size [in]

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## -returns



None




## -remarks



In the course of normal network operations, a stand-alone CM calls 
    <b>NdisCmDispatchIncomingCloseCall</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because the corresponding client on the remote node has
    called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>.

However, a call manager also can call 
    <b>NdisCmDispatchIncomingCloseCall</b> if either of the following occurs:

<ul>
<li>
The call manager has notified a client of an incoming call offer. When the CM's 
      <a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
      ProtocolCmIncomingCallComplete</a> function is called with the client's acceptance, it validates the
      input call parameters, which that client has modified. 
      <i>ProtocolCmIncomingCallComplete</i> determines that the client is proposing unsupportable call
      parameters for the connection, so it calls 
      <b>NdisCmDispatchIncomingCloseCall</b>.

</li>
<li>
Abormal network conditions force the call manager to tear down active calls. For example, if the
      call manager is notified when any link on the connection between this client and the remote party to
      the connection goes down, the CM would call 
      <b>NdisCmDispatchIncomingCloseCall</b> to prevent the client from attempting (or expecting) further data
      transfers on such a broken connection.

</li>
</ul>
After tearing down any call, the original creator of the VC is responsible for calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a> after releasing any
    additional resources it had associated with the VC.

A call to 
    <b>NdisCmDispatchIncomingCloseCall</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">
    ProtocolClIncomingCloseCall</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCloseCall</b>. Connection-oriented miniport drivers that provide call-management
    support call 
    <a href="https://msdn.microsoft.com/24102e1f-375e-4bf4-8a43-6527b90c8564">
    NdisMCmDispatchIncomingCall</a> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/9dce2b0a-1d0c-4c87-a32f-8bf72bb91cfe">
   NdisCmDispatchIncomingDropParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>



<a href="https://msdn.microsoft.com/843050e1-a1ec-4313-b527-529c4ff6ca07">
   NdisMCmDispatchIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">ProtocolClIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/1755804c-d82f-465d-862f-8a2340516f8e">
   ProtocolCoReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/1416ad56-548c-4f12-9922-9ab9a7e4fd3a">ProtocolCoStatusEx</a>
 

 

