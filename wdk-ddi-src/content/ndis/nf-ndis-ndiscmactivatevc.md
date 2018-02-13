---
UID: NF:ndis.NdisCmActivateVc
title: NdisCmActivateVc function
author: windows-driver-content
description: NdisCmActivateVc passes CM-supplied call parameters, including media parameters, for a particular VC down to the underlying miniport driver.
old-location: netvista\ndiscmactivatevc.htm
old-project: netvista
ms.assetid: 9091426c-3174-4367-b7c7-5684877efe9c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: condis_call_manager_ref_425eba15-2cda-4e36-b88d-59978501ecbf.xml, netvista.ndiscmactivatevc, NdisCmActivateVc function [Network Drivers Starting with Windows Vista], NdisCmActivateVc, ndis/NdisCmActivateVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmActivateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmActivateVc (NDIS 5.1)) in   Windows XP.
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
-	NdisCmActivateVc
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisCmActivateVc function


## -description


<b>NdisCmActivateVc</b> passes CM-supplied call parameters, including media parameters, for a particular VC
  down to the underlying miniport driver.


## -syntax


````
NDIS_STATUS NdisCmActivateVc(
  _In_    NDIS_HANDLE         NdisVcHandle,
  _Inout_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC on which to set call parameters. The call manager either
     obtained this handle from 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> for an incoming call or as
     an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function for a
     client-initiated outgoing call.


### -param CallParameters [in, out]

Pointer to a CM-allocated resident buffer, formatted as a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, containing all the
     media-specific parameters that the underlying miniport driver uses for VC activation.


## -returns



When 
     <b>NdisCmActivateVc</b> returns anything other than NDIS_STATUS_PENDING, the call manager should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
     ProtocolCmActivateVcComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmActivateVcComplete</i> function when this operation is completed.




## -remarks



<b>NdisCmActivateVc</b> notifies the underlying miniport driver to set up call and media parameters on a
    newly created VC or to change those of an established VC. NDIS forwards the given call parameters and VC
    handle to the underlying miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a> function, which
    sets up all necessary resources to track the state of the VC and makes itself and a NIC ready for data
    transfers on the VC.

A stand-alone CM always calls 
    <b>NdisCmActivateVc</b> after establishing a connection on a VC but before any data is sent or received on
    that VC. For the duration of the connection, a CM can call 
    <b>NdisCmActivateVc</b> many times with the same 
    <i>NdisVcHandle</i> as conditions on the network change and/or whenever the client calls 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>. At each such
    call to 
    <b>NdisCmActivateVc</b>, the underlying miniport driver's 
    <i>MiniportCoActivateVc</i> function must do either of the following:

<ul>
<li>
Update the state that the miniport driver maintains about call parameters to the new values supplied
      by the call manager if the miniport driver can continue to make transfers on the VC according to the
      newly modified call parameters.

</li>
<li>
Fail the call if the miniport driver cannot continue to make transfers under the constraints of the
      given call parameters.

</li>
</ul>
When the underlying miniport driver fails a request to set or reset call parameters, the call manager
    might modify its original specification at 
    <i>CallParameters</i> and call 
    <b>NdisCmActivateVc</b> again. The limit on the number of times any call manager makes repeated attempts
    to activate a VC is implementation-dependent.

For a client-initiated outgoing call, a stand-alone CM usually calls 
    <b>NdisCmActivateVc</b> immediately following the packet exchange confirming a negotiated agreement with
    the remote target of the call or successful call-setup at the switch, before it notifies NDIS (and the
    client) of outgoing call completion with 
    <a href="..\ndis\nf-ndis-ndiscmmakecallcomplete.md">NdisCmMakeCallComplete</a>. For an
    incoming call, a call manager usually calls 
    <b>NdisCmActivateVc</b> after it has called 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> successfully and before it
    calls 
    <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
    NdisCmDispatchIncomingCall</a>.

In the process of setting up an outgoing call and while any VC remains activated, the client can
    request changes to the call parameters for that VC, for example, by calling 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQos</a>. After verifying
    the validity of the given call parameters for any such a request, the stand-alone call manager must call 
    <b>NdisCmActivateVc</b> to pass the modified call parameters down to the underlying miniport driver.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmActivateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <b>NdisMCmActivateVc</b> instead.




## -see-also

<a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
   ProtocolCmActivateVcComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQos</a>



<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>



<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmActivateVc function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

