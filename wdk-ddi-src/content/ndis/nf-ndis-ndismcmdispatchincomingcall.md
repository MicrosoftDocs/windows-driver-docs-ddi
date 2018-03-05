---
UID: NF:ndis.NdisMCmDispatchIncomingCall
title: NdisMCmDispatchIncomingCall macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client with the MCM driver.
old-location: netvista\ndismcmdispatchincomingcall.htm
old-project: netvista
ms.assetid: 24102e1f-375e-4bf4-8a43-6527b90c8564
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
req.lib: ndis.h
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDispatchIncomingCall macro


## -description


<b>NdisMCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client with the MCM driver.


## -syntax


````
NDIS_STATUS NdisMCmDispatchIncomingCall(
  [in] NDIS_HANDLE         NdisSapHandle,
  [in] NDIS_HANDLE         NdisVcHandle,
  [in] PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param _SH_

TBD


### -param _VH_

TBD


### -param _CP_

TBD






#### - NdisSapHandle [in]

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>, and the MCM driver
     obtained this handle as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


#### - NdisVcHandle [in]

Specifies the handle identifying the VC, created with 
     <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a> when the MCM driver
     processes the incoming call offer directed to this registered SAP.


#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     and media parameters for the VC.


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
      <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>


</li>
<li>
Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

</li>
<li>
Activated the VC with 
      <a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a> to notify NDIS that
      it is ready for transfers on the VC in accord with the negotiated or accepted call parameters

</li>
</ul>
The MCM driver's call to 
    <b>NdisMCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingCall</i> function, within which the client either accepts or rejects the requested
    connection. After deciding whether to accept the connection, the client calls 
    <a href="..\ndis\nf-ndis-ndisclincomingcallcomplete.md">NdisClIncomingCallComplete</a>,
    which, in turn, calls the MCM driver's 
    <i>ProtocolCmIncomingCallComplete</i> function. If the client accepted the call, the MCM driver next calls
    
    <a href="..\ndis\nf-ndis-ndismcmdispatchcallconnected.md">
    NdisMCmDispatchCallConnected</a>. Otherwise, it deactivates (and possibly deletes) the VC it created,
    after notifying the remote node that the offered call was rejected.

Only connection-oriented miniport drivers that provide integrated call-management support call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCall</b> instead.




## -see-also

<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
   ProtocolCmIncomingCallComplete</a>



<a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a>



<a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>



<a href="..\ndis\nf-ndis-ndismcmdeactivatevc.md">NdisMCmDeactivateVc</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisclincomingcallcomplete.md">NdisClIncomingCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nf-ndis-ndismcmdispatchcallconnected.md">NdisMCmDispatchCallConnected</a>



<a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDispatchIncomingCall macro%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

