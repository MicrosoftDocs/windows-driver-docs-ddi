---
UID: NF:ndis.NdisMCmDispatchIncomingCall
title: NdisMCmDispatchIncomingCall macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client with the MCM driver.
old-location: netvista\ndismcmdispatchincomingcall.htm
old-project: netvista
ms.assetid: 24102e1f-375e-4bf4-8a43-6527b90c8564
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmDispatchIncomingCall, NdisMCmDispatchIncomingCall macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_1133faf8-d5a6-4800-8738-94b11bc1d51f.xml, ndis/NdisMCmDispatchIncomingCall, netvista.ndismcmdispatchincomingcall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows XP.
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
-	NdisMCmDispatchIncomingCall
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDispatchIncomingCall macro


## -description


<b>NdisMCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client with the MCM driver.


## -parameters




### -param _SH_

TBD


### -param _VH_

TBD


### -param _CP_

TBD






#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     and media parameters for the VC.


#### - NdisSapHandle [in]

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>, and the MCM driver
     obtained this handle as an input parameter to its 
     <a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">
     ProtocolCmRegisterSap</a> function.


#### - NdisVcHandle [in]

Specifies the handle identifying the VC, created with 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a> when the MCM driver
     processes the incoming call offer directed to this registered SAP.


## -remarks



Before calling 
    <b>NdisMCmDispatchIncomingCall</b>, an MCM driver has already done the following:

<ul>
<li>
Identified the target SAP, previously registered by a particular client, for the call (actually, a
      request to make a connection) that it received over the network

</li>
<li>
Created a VC for the incoming call with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>


</li>
<li>
Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

</li>
<li>
Activated the VC with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a> to notify NDIS that
      it is ready for transfers on the VC in accord with the negotiated or accepted call parameters

</li>
</ul>
The MCM driver's call to 
    <b>NdisMCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingCall</i> function, within which the client either accepts or rejects the requested
    connection. After deciding whether to accept the connection, the client calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561632">NdisClIncomingCallComplete</a>,
    which, in turn, calls the MCM driver's 
    <i>ProtocolCmIncomingCallComplete</i> function. If the client accepted the call, the MCM driver next calls
    
    <a href="https://msdn.microsoft.com/b47976ad-fdde-48cb-bb30-4eaf25489143">
    NdisMCmDispatchCallConnected</a>. Otherwise, it deactivates (and possibly deletes) the VC it created,
    after notifying the remote node that the offered call was rejected.

Only connection-oriented miniport drivers that provide integrated call-management support call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCall</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/345715fb-878c-44d8-bf78-f3add10dd02b">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561632">NdisClIncomingCallComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561664">NdisCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562826">NdisMCmDispatchCallConnected</a>



<a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a>



<a href="https://msdn.microsoft.com/353e929b-17c8-47e8-82fd-b646e93a5b9a">
   ProtocolCmIncomingCallComplete</a>



<a href="https://msdn.microsoft.com/3e3e7a0e-a8d2-40b2-895b-187d24867080">ProtocolCmRegisterSap</a>
 

 

