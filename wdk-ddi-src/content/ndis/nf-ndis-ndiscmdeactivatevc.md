---
UID: NF:ndis.NdisCmDeactivateVc
title: NdisCmDeactivateVc function
author: windows-driver-content
description: NdisCmDeactivateVc notifies NDIS and the underlying miniport driver that there will be no further transfers on a particular active VC.
old-location: netvista\ndiscmdeactivatevc.htm
old-project: netvista
ms.assetid: 141830de-e113-4f42-91f8-8f1cdbf3e32c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisCmDeactivateVc function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_3d365bcf-91cc-4724-a4af-77e9bea6fe0c.xml, ndis/NdisCmDeactivateVc, netvista.ndiscmdeactivatevc, NdisCmDeactivateVc
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCmDeactivateVc
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisCmDeactivateVc function


## -description


<b>NdisCmDeactivateVc</b> notifies NDIS and the underlying miniport driver that there will be no further
  transfers on a particular active VC.


## -syntax


````
NDIS_STATUS NdisCmDeactivateVc(
  _In_ NDIS_HANDLE NdisVcHandle
);
````


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC. This handle was supplied by NDIS to the call manager
     either when it called 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> for an incoming call or
     when its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function set up
     the VC for a client-initiated outgoing call.


## -returns



When 
     <b>NdisCmDeactivateVc</b> returns anything other than NDIS_STATUS_PENDING, the call manager should make
     an internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
     ProtocolCmDeactivateVcComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmDeactivateVcComplete</i> function when this operation is completed.




## -remarks



A stand-alone call manager calls 
    <b>NdisCmDeactivateVc</b> as an essential step in closing a call, usually after the packet exchange with
    network components that tears down the call.

A call to 
    <b>NdisCmDeactivateVc</b> causes NDIS to call the underlying miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">MiniportCoDeactivateVc</a> function,
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
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.

</li>
<li>
Following VC deactivation and the closing of the call, a CM can reuse a VC that it originally
      created to indicate another incoming call to the same client with 
      <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
      NdisCmDispatchIncomingCall</a>.

</li>
</ul>
The creator of a particular VC that will not be reused calls 
    <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a> to destroy that VC.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDeactivateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <b>NdisMCmDeactivateVc</b> instead.




## -see-also

<a href="..\ndis\nf-ndis-ndismcmdeactivatevc.md">NdisMCmDeactivateVc</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
   ProtocolCmDeactivateVcComplete</a>



<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">MiniportCoDeactivateVc</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmDeactivateVc function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

