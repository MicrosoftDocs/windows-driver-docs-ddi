---
UID: NF:ndis.NdisCmDeregisterSapComplete
title: NdisCmDeregisterSapComplete function
author: windows-driver-content
description: NdisCmDeregisterSapComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to deregister a SAP.
old-location: netvista\ndiscmderegistersapcomplete.htm
old-project: netvista
ms.assetid: 92955e1e-6c5b-4e8e-a365-65ff4d0889a5
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisCmDeregisterSapComplete, NdisCmDeregisterSapComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_d8a656de-56d5-4b84-8179-636b72f1313b.xml, ndis/NdisCmDeregisterSapComplete, netvista.ndiscmderegistersapcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP.
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
-	NdisCmDeregisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDeregisterSapComplete function


## -description


<b>NdisCmDeregisterSapComplete</b> returns the final status of a client's request, for which the call
  manager previously returned NDIS_STATUS_PENDING, to deregister a SAP.


## -parameters




### -param Status [in]

Specifies NDIS_STATUS_SUCCESS.


### -param NdisSapHandle [in]

Specifies the handle identifying the SAP.


## -returns



None




## -remarks



<b>NdisCmDeregisterSapComplete</b> notifies both NDIS and the client that the call manager has completed
    the SAP-deregistration request for which its 
    <a href="https://msdn.microsoft.com/738c426e-aa4f-4f59-b955-fbf67071303f">
    ProtocolCmDeregisterSap</a> function previously returned NDIS_STATUS_PENDING.

A call to 
    <b>NdisCmDeregisterSapComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6">
    ProtocolClDeregisterSapComplete</a> function.

The call manager should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisCmDeregisterSapComplete</b> returns control.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDeregisterSapComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDeregisterSapComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562821">NdisMCmDeregisterSapComplete</a>



<a href="https://msdn.microsoft.com/93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6">
   ProtocolClDeregisterSapComplete</a>



<a href="https://msdn.microsoft.com/738c426e-aa4f-4f59-b955-fbf67071303f">ProtocolCmDeregisterSap</a>
 

 

