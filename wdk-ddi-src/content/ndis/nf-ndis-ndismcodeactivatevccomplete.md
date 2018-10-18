---
UID: NF:ndis.NdisMCoDeactivateVcComplete
title: NdisMCoDeactivateVcComplete function
author: windows-driver-content
description: NdisMCoDeactivateVcComplete notifies NDIS and the call manager that the miniport driver has finished processing a CM-initiated deactivate-VC request, for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location: netvista\ndismcodeactivatevccomplete.htm
tech.root: netvista
ms.assetid: 8ea36895-4728-45ad-84f7-3517afd2327d
ms.date: 5/2/2018
ms.keywords: NdisMCoDeactivateVcComplete, NdisMCoDeactivateVcComplete function [Network Drivers Starting with Windows Vista], condis_miniport_ref_b4ad1f67-6e33-45ca-9d55-323aed8820be.xml, ndis/NdisMCoDeactivateVcComplete, netvista.ndismcodeactivatevccomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows XP.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMCoDeactivateVcComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCoDeactivateVcComplete function


## -description


<b>NdisMCoDeactivateVcComplete</b> notifies NDIS and the call manager that the miniport driver has finished
  processing a CM-initiated deactivate-VC request, for which the miniport driver previously returned
  NDIS_STATUS_PENDING.


## -parameters




### -param Status [in]

Specifies the final status of the deactivate-VC operation, which can be NDIS_STATUS_SUCCESS or any
     NDIS_STATUS_
     <i>XXX except</i> NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle identifying the VC. The caller obtained this handle from its per-VC state,
     designated by the 
     <i>MiniportVcContext</i> passed as an input parameter to its 
     <a href="https://msdn.microsoft.com/8c17cec8-d161-47cf-b886-bb8b8d957656">
     MiniportCoDeactivateVc</a> function.


## -returns



None




## -remarks



A connection-oriented miniport driver must call 
    <b>NdisMCoDeactivateVcComplete</b> if its 
    <i>MiniportCoDeactivateVc</i> function previously returned NDIS_STATUS_PENDING in response to a request to
    deactivate the VC identified by the given 
    <i>NdisVcHandle</i> . The call manager, which initiated the VC deactivation with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a>, cannot notify NDIS
    or its client whether transfers have been disabled on the VC until the miniport driver calls 
    <b>NdisMCoDeactivateVcComplete</b>.

Before it deactivates a VC, the miniport driver must complete any pending transfers on the VC. That
    is, the miniport driver must indicate all outstanding receives and transmit all outstanding sends before
    calling 
    <b>NdisMCoDeactivateVcComplete</b>.

A call to 
    <b>NdisMCoDeactivateVcComplete</b> causes NDIS to call the 
    <a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
    ProtocolCmDeactivateVcComplete</a> function of the call manager that originally requested the VC
    deactivation. Following its call to 
    <b>NdisMCoDeactivateVcComplete</b>, the miniport driver can neither indicate receives nor transmit sends
    on the VC.




## -see-also




<a href="https://msdn.microsoft.com/8c17cec8-d161-47cf-b886-bb8b8d957656">MiniportCoDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/44ee0e3c-aee9-4e24-9e54-c57248b568b6">
   ProtocolCmDeactivateVcComplete</a>
 

 

