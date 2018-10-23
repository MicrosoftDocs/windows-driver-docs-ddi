---
UID: NF:ndis.NdisMCmMakeCallComplete
title: NdisMCmMakeCallComplete macro
author: windows-driver-content
description: NdisMCmMakeCallComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to make an outgoing call.
old-location: netvista\ndismcmmakecallcomplete.htm
tech.root: netvista
ms.assetid: b518f36e-5937-4a74-a1d4-9e1709750843
ms.date: 05/02/2018
ms.keywords: NdisMCmMakeCallComplete, NdisMCmMakeCallComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_685b4f14-92ef-4c46-a11f-19b34d59734c.xml, ndis/NdisMCmMakeCallComplete, netvista.ndismcmmakecallcomplete
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmMakeCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmMakeCallComplete (NDIS   5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmMakeCallComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmMakeCallComplete macro


## -description


<b>NdisMCmMakeCallComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to make an outgoing call.


## -parameters




### -param _S_

Specifies the final status of the attempt to make the connection, either NDIS_STATUS_SUCCESS or
     any caller-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.

### -param _VH_

Specifies the handle to the client-created VC, which the MCM driver obtained as an input parameter
     to its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function and,
     more recently, from the 
     <i>CallMgrVcContext</i> passed to its 
     <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function.

### -param _PH_

Specifies the handle to the initial party on the client-created multipoint VC, which the MCM
     driver obtained as an input parameter to its 
     <i>ProtocolCmMakeCall</i> function. If the given 
     <i>NdisVcHandle</i> represented a point-to-point VC, this parameter was <b>NULL</b>.

### -param _CC_

Specifies the handle to a caller-allocated resident context area, in which the MCM driver will
     maintain per-party state information, or this parameter is <b>NULL</b> if 
     <i>NdisPartyHandle</i> is <b>NULL</b>. For a multipoint VC, NDIS passes this MCM-driver-supplied 
     <i>CallManagerPartyContext</i> handle in all subsequent calls to the ProtocolCm<i>Xxx</i> functions that concern this party. If 
     <i>Status</i> is anything other than NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


### -param _CP_

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     parameters set up for this connection if 
     <i>Status</i> is NDIS_STATUS_SUCCESS.

## -remarks



An MCM driver should call 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS only if it is ready to make data transfers on the
    VC. That is, the MCM driver has negotiated with the network to establish the call parameters for the VC,
    set up a NIC for those call parameters, and called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562792">NdisMCmActivateVc</a> to notify NDIS of the
    VC activation.

An MCM driver must call 
    <b>NdisMCmMakeCallComplete</b> if its 
    <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function
    previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisVcHandle</i> .The client, which initiated the pending outgoing call, cannot use the VC to make
    transfers until the miniport driver calls 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS.

Even if the attempted connection failed, neither NDIS nor the client can release the resources they
    allocated to maintain state until the MCM driver's call to 
    <b>NdisMCmMakeCallComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">
    ProtocolClMakeCallComplete</a> function. In fact, neglecting to call 
    <b>NdisMCmMakeCallComplete</b> for a failed attempt to set up such a connection causes a memory leak in
    the MCM driver as well; it prevents the client from tearing down the VC it created for its failed
    outgoing call, so the MCM driver's 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function is not
    called to release the resources the miniport driver allocated for that VC.

If the MCM driver passes an error, such as NDIS_STATUS_FAILURE, for the 
    <i>Status</i>, it must consider the 
    <i>NdisPartyHandle</i>, if any, invalid when 
    <b>NdisMCmMakeCallComplete</b> returns control. The CM can release (or reinitialize for reuse) any
    resources that it allocated to maintain state for the given party after 
    <b>NdisMCmMakeCallComplete</b> returns control. The MCM driver's 
    <i>ProtocolCoDeleteVc</i> function will subsequently be called to release any resources that the miniport
    driver allocated for tracking the state of the client-created VC whenever the MCM driver passes an error
    status to 
    <b>NdisMCmMakeCallComplete</b>.

In the course of setting up a client-initiated outgoing call, the MCM driver can modify the
    client-supplied call parameters originally passed in to its 
    <i>ProtocolCmMakeCall</i> function. If it does, the MCM driver must pass its modifications in the buffer
    at 
    <i>CallParameters</i> when it calls 
    <b>NdisMCmMakeCallComplete</b>. If the client finds these modified call parameters unacceptable, it will
    then tear down the call, which also causes a call to the MCM driver's 
    <i>ProtocolCoDeleteVc</i> function.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmMakeCallComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmMakeCallComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561677">NdisCmMakeCallComplete</a>



<a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">ProtocolClMakeCallComplete</a>



<a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

