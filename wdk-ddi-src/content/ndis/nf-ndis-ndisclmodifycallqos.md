---
UID: NF:ndis.NdisClModifyCallQoS
title: NdisClModifyCallQoS function (ndis.h)
description: NdisClModifyCallQoS requests a change in the quality of service on a connection.
old-location: netvista\ndisclmodifycallqos.htm
tech.root: netvista
ms.assetid: c31449a6-e275-480c-83ea-8575fda73cd9
ms.date: 05/02/2018
keywords: ["NdisClModifyCallQoS function"]
ms.keywords: NdisClModifyCallQoS, NdisClModifyCallQoS function [Network Drivers Starting with Windows Vista], condis_client_ref_55b0158f-e91e-4be8-818b-ade726db0f61.xml, ndis/NdisClModifyCallQoS, netvista.ndisclmodifycallqos
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisClModifyCallQoS
 - ndis/NdisClModifyCallQoS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisClModifyCallQoS
---

# NdisClModifyCallQoS function


## -description

<b>NdisClModifyCallQoS</b> requests a change in the quality of service on a connection.

## -parameters

### -param NdisVcHandle 

[in]
Specifies the handle to the VC for which the client wants to modify the QoS. The client originally
     obtained this handle by calling 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>, and, more recently,
     retrieved this handle from its per-VC state area.

### -param CallParameters 

[in]
Pointer to a structure of type CO_CALL_PARAMETERS that specifies the new QoS requested by the
     caller.

## -returns

When 
     <b>NdisClModifyCallQoS</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_modify_call_qos_complete">
     ProtocolClModifyCallQoSComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClModifyCallQoSComplete</i> function when this operation is completed.

## -remarks

A call to 
    <b>NdisClModifyCallQoS</b> causes NDIS to call the CM's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_modify_qos_call">
    ProtocolCmModifyCallQoS</a> function, which, in turn, calls 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a> to notify the underlying
    miniport driver to change the call parameters if the requested QoS change can be made.

If the call manager does not accept the client's proposed QoS change, the client either can continue
    using the unchanged QoS for the call or can tear down the call. If the client and call manager cannot
    agree on the QoS for a particular call, the creator of the VC is responsible for initiating the teardown
    of the VC.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmmodifycallqoscomplete">NdisCmModifyCallQoSComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_modify_call_qos_complete">
   ProtocolClModifyCallQoSComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_modify_qos_call">ProtocolCmModifyCallQoS</a>