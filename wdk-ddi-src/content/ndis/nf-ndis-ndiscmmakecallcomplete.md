---
UID: NF:ndis.NdisCmMakeCallComplete
title: NdisCmMakeCallComplete function (ndis.h)
description: NdisCmMakeCallComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to make an outgoing call.
old-location: netvista\ndiscmmakecallcomplete.htm
tech.root: netvista
ms.assetid: e2c1f849-daf0-479c-9f1d-906149ac550e
ms.date: 05/02/2018
ms.keywords: NdisCmMakeCallComplete, NdisCmMakeCallComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_15c2bbda-e3f5-41dd-96a1-4466852ed244.xml, ndis/NdisCmMakeCallComplete, netvista.ndiscmmakecallcomplete
ms.topic: function
f1_keywords:
 - "ndis/NdisCmMakeCallComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmMakeCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmMakeCallComplete (NDIS   5.1)) in Windows XP.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCmMakeCallComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmMakeCallComplete function


## -description


<b>NdisCmMakeCallComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to make an outgoing call.


## -parameters




### -param Status [in]

Specifies the final status of the attempt to make the connection, either NDIS_STATUS_SUCCESS or
     any CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle to the client-created VC, which the call manager originally obtained as an
     input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function. More
     recently, the CM obtained this handle from its per-VC state designated by the 
     <i>CallMgrVcContext</i> passed in to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a> function.


### -param NdisPartyHandle [in, optional]

Specifies the handle to the initial party on the client-created multipoint VC, which the call
     manager obtained as an input parameter to its 
     <i>ProtocolCmMakeCall</i> function. If the given 
     <i>NdisVcHandle</i> represented a point-to-point VC, this parameter was <b>NULL</b>.


### -param CallMgrPartyContext [in, optional]

Specifies the CM-supplied handle to a caller-allocated resident context area, in which the CM will
     maintain per-party state information, or <b>NULL</b> if 
     <i>NdisPartyHandle</i> is <b>NULL</b>. For a multipoint VC, NDIS passes this CM-supplied 
     <i>CallManagerPartyContext</i> handle in all subsequent calls to the ProtocolCm<i>Xxx</i> functions that concern this party. Otherwise, NDIS ignores this parameter.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that specifies the call
     parameters set up for this connection if 
     <i>Status</i> is NDIS_STATUS_SUCCESS.


## -returns



None




## -remarks



A stand-alone call manager should call 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS only if the underlying miniport driver is ready to
    make data transfers on the VC. That is, the call manager has negotiated with the network to establish
    call parameters for the VC and called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a> successfully.

A stand-alone call manager must call 
    <b>NdisCmMakeCallComplete</b> if its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a> function
    previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisVcHandle</i> . The client that initiated the pending outgoing call cannot use the VC to make
    transfers until the CM calls 
    <b>NdisCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS.

Even if the attempted connection failed, neither NDIS nor the client can release the resources they
    allocated to maintain state until the CM's call to 
    <b>NdisCmMakeCallComplete</b> causes a call to that client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_make_call_complete">
    ProtocolClMakeCallComplete</a> function. In fact, neglecting to call 
    <b>NdisCmMakeCallComplete</b> for a failed attempt to set up such a connection causes a memory leak in the
    call manager as well; it prevents the client from tearing down the VC it created for its failed outgoing
    call, so the CM is not called to release the resources it allocated for that VC.

If the CM passes an error, such as NDIS_STATUS_FAILURE, for the 
    <i>Status</i>, it should consider the 
    <i>NdisPartyHandle</i>, if any, invalid as soon as it calls 
    <b>NdisCmMakeCallComplete</b>. The CM can release (or reinitialize for reuse) any resources that it
    allocated to maintain state for the given party when 
    <b>NdisCmMakeCallComplete</b> returns control. The CM's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function will
    subsequently be called to release any resources that the CM allocated for tracking the state of the
    client-created VC whenever the CM passes an error status to 
    <b>NdisCmMakeCallComplete</b>.

In the course of setting up a client-initiated outgoing call, the CM can modify the client-supplied
    call parameters originally passed in to its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a> function. If it
    does, the CM must pass its modifications in the buffer at 
    <i>CallParameters</i> when it calls 
    <b>NdisCmMakeCallComplete</b>. If the client finds these modified call parameters unacceptable, it will
    then tear down the call, which also causes a call to the CM's 
    <i>ProtocolCoDeleteVc</i> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmMakeCallComplete</b>. Miniport drivers that provide integrated call-management support call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmmakecallcomplete">
    NdisMCmMakeCallComplete</a> instead.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmmakecallcomplete">NdisMCmMakeCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_make_call_complete">ProtocolClMakeCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

