---
UID: NF:ndis.NdisCmDeactivateVc
title: NdisCmDeactivateVc function
author: windows-driver-content
description: NdisCmDeactivateVc notifies NDIS and the underlying miniport driver that there will be no further transfers on a particular active VC.
old-location: netvista\ndiscmdeactivatevc.htm
tech.root: netvista
ms.assetid: 141830de-e113-4f42-91f8-8f1cdbf3e32c
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisCmDeactivateVc, NdisCmDeactivateVc function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_3d365bcf-91cc-4724-a4af-77e9bea6fe0c.xml, ndis/NdisCmDeactivateVc, netvista.ndiscmdeactivatevc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDeactivateVc (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDeactivateVc (NDIS 5.1))   in Windows XP.
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
-	NdisCmDeactivateVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDeactivateVc function


## -description


<b>NdisCmDeactivateVc</b> notifies NDIS and the underlying miniport driver that there will be no further
  transfers on a particular active VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC. This handle was supplied by NDIS to the call manager
     either when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a> for an incoming call or
     when its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function set up
     the VC for a client-initiated outgoing call.


## -returns



When 
     <b>NdisCmDeactivateVc</b> returns anything other than NDIS_STATUS_PENDING, the call manager should make
     an internal call to its 
     <a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
     ProtocolCmDeactivateVcComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmDeactivateVcComplete</i> function when this operation is completed.




## -remarks



A stand-alone call manager calls 
    <b>NdisCmDeactivateVc</b> as an essential step in closing a call, usually after the packet exchange with
    network components that tears down the call.

A call to 
    <b>NdisCmDeactivateVc</b> causes NDIS to call the underlying miniport driver's 
    <a href="https://msdn.microsoft.com/8c17cec8-d161-47cf-b886-bb8b8d957656">MiniportCoDeactivateVc</a> function,
    which can discard the current call parameters for transfers on the VC, possibly reinitializing them to
    miniport driver-determined default values. If the VC is reactivated subsequently for another call, the
    client or call manager will supply new call parameters to the miniport driver.

The 
    <i>NdisVcHandle</i> passed to 
    <b>NdisCmDeactivateVc</b> remains valid after VC deactivation is completed. The deactivation of any VC
    allows its creator to reinitialize the VC for reuse:

<ul>
<li>
Following VC deactivation and the closing of the call, a client can reuse a VC that it originally
      created to make another call with 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>.

</li>
<li>
Following VC deactivation and the closing of the call, a CM can reuse a VC that it originally
      created to indicate another incoming call to the same client with 
      <a href="https://msdn.microsoft.com/2172aeec-8502-414e-9d01-9292c0eb7ce8">
      NdisCmDispatchIncomingCall</a>.

</li>
</ul>
The creator of a particular VC that will not be reused calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a> to destroy that VC.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDeactivateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <b>NdisMCmDeactivateVc</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/8c17cec8-d161-47cf-b886-bb8b8d957656">MiniportCoDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561664">NdisCmDispatchIncomingCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a>



<a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
   ProtocolCmDeactivateVcComplete</a>
 

 

