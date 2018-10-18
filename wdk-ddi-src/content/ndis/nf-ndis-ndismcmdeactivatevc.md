---
UID: NF:ndis.NdisMCmDeactivateVc
title: NdisMCmDeactivateVc function
author: windows-driver-content
description: NdisMCmDeactivateVc notifies NDIS that there will be no further transfers on a particular active VC.
old-location: netvista\ndismcmdeactivatevc.htm
tech.root: netvista
ms.assetid: e18f6326-621e-4bed-aa82-b326f3b1422d
ms.date: 5/2/2018
ms.keywords: NdisMCmDeactivateVc, NdisMCmDeactivateVc function [Network Drivers Starting with Windows Vista], condis_mcm_ref_c1aa796e-7965-4a4b-849b-370ae7f95697.xml, ndis/NdisMCmDeactivateVc, netvista.ndismcmdeactivatevc
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeactivateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeactivateVc (NDIS   5.1)) in Windows XP.
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
-	NdisMCmDeactivateVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDeactivateVc function


## -description


<b>NdisMCmDeactivateVc</b> notifies NDIS that there will be no further transfers on a particular active
  VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC. This handle was supplied by NDIS to the MCM driver either
     when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a> for an incoming call or
     when its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function set up
     the VC for a client-initiated outgoing call.


## -returns



<b>NdisMCmDeactivateVc</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS marked the VC as inactive.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The VC is already deactivated, so this call is redundant.

</td>
</tr>
</table>
 




## -remarks



An MCM driver calls 
    <b>NdisMCmDeactivateVc</b> as an essential step in closing a call, usually after the packet exchange with
    network components that tears down the connection.

A successful call to 
    <b>NdisMCmDeactivateVc</b> allows the MCM driver to discard the current call parameters for transfers on
    the VC, possibly reinitializing them to miniport driver-determined default values. However, if the VC is
    reactivated subsequently for another call, the client will supply new call parameters to the miniport
    driver.

The 
    <i>NdisVcHandle</i> passed to 
    <b>NdisMCmDeactivateVc</b> remains valid after VC deactivation is completed. The deactivation of any VC
    allows its creator to reinitialize the VC for reuse or to destroy it:

<ul>
<li>
Following VC deactivation and the closing of the call, a client can reuse a VC that it originally
      created to make another call with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>, or it can call 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>, thereby causing a call
      to the MCM driver's 
      <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function.

</li>
<li>
Following VC deactivation and the closing of the call, an MCM driver can reuse a VC that it
      originally created to indicate another incoming call to the same client with 
      <a href="https://msdn.microsoft.com/24102e1f-375e-4bf4-8a43-6527b90c8564">
      NdisMCmDispatchIncomingCall</a>, or it can call 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a>.

</li>
</ul>
The driver writer determines whether an MCM driver has an (internal) 
    <i>MiniportCoDeactivateVc</i> function that the driver calls in the context of tearing down connections
    for outgoing and incoming calls.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeactivateVc</b>. Stand-alone call managers, which register themselves with NDIS as protocol
    drivers, call 
    <b>NdisCmDeactivateVc</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/8c17cec8-d161-47cf-b886-bb8b8d957656">MiniportCoDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562830">NdisMCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

