---
UID: NF:ndis.NdisClModifyCallQoS
title: NdisClModifyCallQoS function
author: windows-driver-content
description: NdisClModifyCallQoS requests a change in the quality of service on a connection.
old-location: netvista\ndisclmodifycallqos.htm
tech.root: netvista
ms.assetid: c31449a6-e275-480c-83ea-8575fda73cd9
ms.date: 05/02/2018
ms.keywords: NdisClModifyCallQoS, NdisClModifyCallQoS function [Network Drivers Starting with Windows Vista], condis_client_ref_55b0158f-e91e-4be8-818b-ade726db0f61.xml, ndis/NdisClModifyCallQoS, netvista.ndisclmodifycallqos
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClModifyCallQoS (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClModifyCallQoS (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
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
-	NdisClModifyCallQoS
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClModifyCallQoS function


## -description


<b>NdisClModifyCallQoS</b> requests a change in the quality of service on a connection.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle to the VC for which the client wants to modify the QoS. The client originally
     obtained this handle by calling 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>, and, more recently,
     retrieved this handle from its per-VC state area.


### -param CallParameters [in]

Pointer to a structure of type CO_CALL_PARAMETERS that specifies the new QoS requested by the
     caller.


## -returns



When 
     <b>NdisClModifyCallQoS</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
     ProtocolClModifyCallQoSComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClModifyCallQoSComplete</i> function when this operation is completed.




## -remarks



A call to 
    <b>NdisClModifyCallQoS</b> causes NDIS to call the CM's 
    <a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">
    ProtocolCmModifyCallQoS</a> function, which, in turn, calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a> to notify the underlying
    miniport driver to change the call parameters if the requested QoS change can be made.

If the call manager does not accept the client's proposed QoS change, the client either can continue
    using the unchanged QoS for the call or can tear down the call. If the client and call manager cannot
    agree on the QoS for a particular call, the creator of the VC is responsible for initiating the teardown
    of the VC.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/243a1236-4b8a-4f00-9f14-3142fa81c362">MiniportCoActivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561679">NdisCmModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
   ProtocolClModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">ProtocolCmModifyCallQoS</a>
 

 

