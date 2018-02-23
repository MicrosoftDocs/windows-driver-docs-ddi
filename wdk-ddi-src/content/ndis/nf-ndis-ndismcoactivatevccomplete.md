---
UID: NF:ndis.NdisMCoActivateVcComplete
title: NdisMCoActivateVcComplete function
author: windows-driver-content
description: NdisMCoActivateVcComplete notifies NDIS and the call manager that the miniport driver has finished processing a CM-initiated activate-VC request, for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndismcoactivatevccomplete.htm
old-project: netvista
ms.assetid: db5ff69f-dcae-4016-a078-c8edb2390c6c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndismcoactivatevccomplete, condis_miniport_ref_3a81c66b-8e97-4194-bf90-988ac2fd05b5.xml, ndis/NdisMCoActivateVcComplete, NdisMCoActivateVcComplete, NdisMCoActivateVcComplete function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCoActivateVcComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCoActivateVcComplete (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
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
-	NdisMCoActivateVcComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMCoActivateVcComplete function


## -description


<b>NdisMCoActivateVcComplete</b> notifies NDIS and the call manager that the miniport driver has finished
  processing a CM-initiated activate-VC request, for which the miniport driver previously returned
  NDIS_STATUS_PENDING.


## -syntax


````
VOID NdisMCoActivateVcComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param Status [in]





##### 


### -param NdisVcHandle [in]

Specifies the handle identifying the VC. The caller obtained this handle from its per-VC state,
     designated by the 
     <i>MiniportVcContext</i> passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">
     MiniportCoActivateVc</a> function.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, supplied by the call
     manager, specifying the call and media parameters for the VC activation.


## -returns



None




## -remarks



A connection-oriented miniport driver must call 
    <b>NdisMCoActivateVcComplete</b> if its 
    <i>MiniportCoActivateVc</i> function previously returned NDIS_STATUS_PENDING in response to a request to
    activate or reactivate the VC identified by the given 
    <i>NdisVcHandle</i> . The call manager, which initiated the VC activation with a call to 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>, cannot notify NDIS or
    its client whether transfers on the VC can be made using the supplied call parameters until the miniport
    driver calls 
    <b>NdisMCoActivateVcComplete</b>.

If the miniport driver finds the CM-supplied call parameters unacceptable, it fails the VC activation
    when it calls 
    <b>NdisMCoActivateVcComplete</b>. Failing the initial activation of a VC can cause the protocol that
    created the VC to tear it down. If the miniport driver fails a request to reactivate an established VC
    with new call parameters, it must restore the original call parameters established for that VC. Depending
    on the nature of the network medium, a miniport driver can modify the media parameters if the round-up
    and/or round-down flag(s) are set before it calls 
    <b>NdisMCoActivateVcComplete</b>.

A call to 
    <b>NdisMCoActivateVcComplete</b> causes NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
    ProtocolCmActivateVcComplete</a> function of the call manager that originally requested the VC
    activation.




## -see-also

<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>



<a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
   ProtocolCmActivateVcComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>



<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoActivateVcComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

