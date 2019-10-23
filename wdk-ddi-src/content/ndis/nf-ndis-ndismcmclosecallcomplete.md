---
UID: NF:ndis.NdisMCmCloseCallComplete
title: NdisMCmCloseCallComplete macro (ndis.h)
description: NdisMCmCloseCallComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to tear down a call.
old-location: netvista\ndismcmclosecallcomplete.htm
tech.root: netvista
ms.assetid: 24477865-fb89-4078-99cb-1bf24249c7e2
ms.date: 05/02/2018
ms.keywords: NdisMCmCloseCallComplete, NdisMCmCloseCallComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_78d6cea5-8d8c-49d4-ad57-c41eb63d3a4b.xml, ndis/NdisMCmCloseCallComplete, netvista.ndismcmclosecallcomplete
ms.topic: macro
f1_keywords:
 - "ndis/NdisMCmCloseCallComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmCloseCallComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmCloseCallComplete macro


## -description


<b>NdisMCmCloseCallComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to tear down a call.


## -parameters




### -param _S_

Specifies the final status of the client's request that the MCM driver close the connection,
     either NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.

### -param _VH_

Specifies the handle to the VC for the call. This handle was supplied by NDIS when the VC was
     originally created, whether by the MCM driver with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a> or as an input parameter
     to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param _PH_

Specifies either <b>NULL</b> if the 
     <i>NdisVcHandle</i> represents a point-to-point VC or the handle to the last remaining party on a
     multipoint connection, which the MCM driver obtained from its per-party state designated by the 
     <i>CallMgrPartyContext</i> passed as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">
     ProtocolCmCloseCall</a> function.


## -remarks



If an MCM driver's 
    <i>ProtocolCmCloseCall</i> function returns NDIS_STATUS_PENDING, it must call 
    <b>NdisMCmCloseCallComplete</b> subsequently to notify the client and NDIS that its attempt to break the
    connection has completed, whether successfully or with an error. A call to 
    <b>NdisMCmCloseCallComplete</b> causes NDIS to call the client's 
    <i>ProtocolClCloseCallComplete</i> function.

If it passes NDIS_STATUS_SUCCESS as the 
    <i>Status</i>, the MCM driver should consider the 
    <i>NdisVcHandle</i> (and 
    <i>NdisPartyHandle</i>, if any) unusable for transfers over the network as soon as it calls 
    <b>NdisMCmCloseCallComplete</b>. If the MCM driver originally created the VC, it should call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a> with the same 
    <i>NdisVcHandle</i> that it just passed to 
    <b>NdisMCmCloseCallComplete</b>. If the client created this VC, the MCM driver can expect a call to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function with the    
    <i>ProtocolVcContext</i>, designating its per-VC state in which it has stored the same 
    <i>NdisVcHandle</i>, as an input parameter.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseCallComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmCloseCallComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmclosecallcomplete">NdisCmCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_call_complete">ProtocolClCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

