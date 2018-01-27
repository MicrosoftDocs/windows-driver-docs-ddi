---
UID: NF:ndis.NdisCmMakeCallComplete
title: NdisCmMakeCallComplete function
author: windows-driver-content
description: NdisCmMakeCallComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to make an outgoing call.
old-location: netvista\ndiscmmakecallcomplete.htm
old-project: netvista
ms.assetid: e2c1f849-daf0-479c-9f1d-906149ac550e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisCmMakeCallComplete, condis_call_manager_ref_15c2bbda-e3f5-41dd-96a1-4466852ed244.xml, ndis/NdisCmMakeCallComplete, netvista.ndiscmmakecallcomplete, NdisCmMakeCallComplete function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisCmMakeCallComplete
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisCmMakeCallComplete function


## -description


<b>NdisCmMakeCallComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to make an outgoing call.


## -syntax


````
VOID NdisCmMakeCallComplete(
  _In_     NDIS_STATUS         Status,
  _In_     NDIS_HANDLE         NdisVcHandle,
  _In_opt_ NDIS_HANDLE         NdisPartyHandle,
  _In_opt_ NDIS_HANDLE         CallMgrPartyContext,
  _In_     PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param Status [in]

Specifies the final status of the attempt to make the connection, either NDIS_STATUS_SUCCESS or
     any CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle to the client-created VC, which the call manager originally obtained as an
     input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function. More
     recently, the CM obtained this handle from its per-VC state designated by the 
     <i>CallMgrVcContext</i> passed in to its 
     <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function.


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
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     parameters set up for this connection if 
     <i>Status</i> is NDIS_STATUS_SUCCESS.


## -returns


None



## -remarks


A stand-alone call manager should call 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS only if the underlying miniport driver is ready to
    make data transfers on the VC. That is, the call manager has negotiated with the network to establish
    call parameters for the VC and called 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a> successfully.

A stand-alone call manager must call 
    <b>NdisCmMakeCallComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function
    previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisVcHandle</i> . The client that initiated the pending outgoing call cannot use the VC to make
    transfers until the CM calls 
    <b>NdisCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS.

Even if the attempted connection failed, neither NDIS nor the client can release the resources they
    allocated to maintain state until the CM's call to 
    <b>NdisCmMakeCallComplete</b> causes a call to that client's 
    <mshelp:link keywords="netvista.protocolclmakecallcomplete" tabindex="0"><i>
    ProtocolClMakeCallComplete</i></mshelp:link> function. In fact, neglecting to call 
    <b>NdisCmMakeCallComplete</b> for a failed attempt to set up such a connection causes a memory leak in the
    call manager as well; it prevents the client from tearing down the VC it created for its failed outgoing
    call, so the CM is not called to release the resources it allocated for that VC.

If the CM passes an error, such as NDIS_STATUS_FAILURE, for the 
    <i>Status</i>, it should consider the 
    <i>NdisPartyHandle</i>, if any, invalid as soon as it calls 
    <b>NdisCmMakeCallComplete</b>. The CM can release (or reinitialize for reuse) any resources that it
    allocated to maintain state for the given party when 
    <b>NdisCmMakeCallComplete</b> returns control. The CM's 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function will
    subsequently be called to release any resources that the CM allocated for tracking the state of the
    client-created VC whenever the CM passes an error status to 
    <b>NdisCmMakeCallComplete</b>.

In the course of setting up a client-initiated outgoing call, the CM can modify the client-supplied
    call parameters originally passed in to its 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function. If it
    does, the CM must pass its modifications in the buffer at 
    <i>CallParameters</i> when it calls 
    <b>NdisCmMakeCallComplete</b>. If the client finds these modified call parameters unacceptable, it will
    then tear down the call, which also causes a call to the CM's 
    <i>ProtocolCoDeleteVc</i> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmMakeCallComplete</b>. Miniport drivers that provide integrated call-management support call 
    <mshelp:link keywords="netvista.ndismcmmakecallcomplete" tabindex="0"><b>
    NdisMCmMakeCallComplete</b></mshelp:link> instead.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>

<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>

<a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">ProtocolClMakeCallComplete</a>

<mshelp:link keywords="netvista.ndisallocatefromnpagedlookasidelist" tabindex="0"><b>
   NdisAllocateFromNPagedLookasideList</b></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>

<a href="..\ndis\nf-ndis-ndismcmmakecallcomplete.md">NdisMCmMakeCallComplete</a>

<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmMakeCallComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

