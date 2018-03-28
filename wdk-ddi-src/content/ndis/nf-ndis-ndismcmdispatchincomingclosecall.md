---
UID: NF:ndis.NdisMCmDispatchIncomingCloseCall
title: NdisMCmDispatchIncomingCloseCall macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCloseCall tells a client to tear down an active or offered call, usually because the MCM driver has received a request from the network to close the connection.
old-location: netvista\ndismcmdispatchincomingclosecall.htm
old-project: netvista
ms.assetid: 843050e1-a1ec-4313-b527-529c4ff6ca07
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmDispatchIncomingCloseCall, NdisMCmDispatchIncomingCloseCall macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_b5a94c5f-7483-44dd-8167-6e64f52cada6.xml, ndis/NdisMCmDispatchIncomingCloseCall, netvista.ndismcmdispatchincomingclosecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.
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
-	NdisMCmDispatchIncomingCloseCall
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDispatchIncomingCloseCall macro


## -description


<b>NdisMCmDispatchIncomingCloseCall</b> tells a client to tear down an active or offered call, usually
  because the MCM driver has received a request from the network to close the connection.


## -parameters




### -param _S_

TBD


### -param _H_

TBD


### -param _B_

TBD


### -param _Z_

TBD






#### - CloseStatus [in]

Specifies a caller-determined NDIS_STATUS_<i>XXX</i>, indicating the reason for the disconnect request. During normal network operations, an MCM
     driver passes NDIS_STATUS_SUCCESS to indicate that it has received a request, initiated by the remote
     party, to close an active call.


#### - NdisVcHandle [in]

Specifies the handle to the VC of the call being disconnected. This handle was supplied by NDIS
     when the VC was originally created, whether by the MCM driver with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a> or as an input parameter
     to its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


#### - Buffer [in, optional]

Pointer to a caller-allocated resident buffer containing additional protocol-specific disconnect
     data, if any. Depending on the underlying medium, this pointer can be <b>NULL</b>.


#### - Size [in]

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## -remarks



In the course of normal network operations, an MCM driver calls 
    <b>NdisMCmDispatchIncomingCloseCall</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because the corresponding client on the remote node has
    called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>.

However, an MCM driver also can call 
    <b>NdisMCmDispatchIncomingCloseCall</b> if either of the following occur:

<ul>
<li>
The MCM driver has notified a client of an incoming call offer. When the miniport driver's 
      <a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
      ProtocolCmIncomingCallComplete</a> function is called with the client's acceptance, it validates the
      input call parameters, which that client has modified. 
      <i>ProtocolCmIncomingCallComplete</i> determines that the client is proposing unsupportable call
      parameters for the connection, so it calls 
      <b>NdisMCmDispatchIncomingCloseCall</b>.

</li>
<li>
Abormal network conditions force the MCM driver to tear down active calls. For example, if the MCM
      driver is notified when any link on the connection between this client and the remote party to the
      connection goes down, the miniport driver would call 
      <b>NdisCmDispatchIncomingCloseCall</b> to prevent the client from attempting (or expecting) further data
      transfers on such a broken connection.

</li>
</ul>
After the client calls 
    <b>NdisClCloseCall</b> thereby causing the deactivation of the VC, the original creator of the VC is
    responsible for destroying the VC. Either the client calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>, which causes NDIS to call
    the MCM driver's 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function, or the
    MCM driver calls 
    <b>NdisMCmDeleteVc</b> after calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a> and releasing any
    additional resources it had associated with the VC that it created.

A call to 
    <b>NdisMCmDispatchIncomingCloseCall</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">
    ProtocolClIncomingCloseCall</a> function.

Only connection-oriented miniport drivers that provide call-management support can call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCloseCall</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562830">NdisMCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/4549b6f4-5138-4724-959c-a36b38c319fd">
   NdisMCmDispatchIncomingDropParty</a>



<a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">ProtocolClIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDispatchIncomingCloseCall macro%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

