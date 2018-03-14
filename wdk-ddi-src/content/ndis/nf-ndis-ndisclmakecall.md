---
UID: NF:ndis.NdisClMakeCall
title: NdisClMakeCall function
author: windows-driver-content
description: NdisClMakeCall sets up an outgoing call on a client-created VC.
old-location: netvista\ndisclmakecall.htm
old-project: netvista
ms.assetid: 69775220-71d8-497c-aaf7-9bc3ec90d00f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisClMakeCall, NdisClMakeCall function [Network Drivers Starting with Windows Vista], condis_client_ref_bd9f0a4a-c8f7-418e-aa80-e97fad7e4ab1.xml, ndis/NdisClMakeCall, netvista.ndisclmakecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClMakeCall (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClMakeCall (NDIS 5.1)) in   Windows XP.
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
-	NdisClMakeCall
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisClMakeCall function


## -description


<b>NdisClMakeCall</b> sets up an outgoing call on a client-created VC.


## -syntax


````
NDIS_STATUS NdisClMakeCall(
  _In_      NDIS_HANDLE         NdisVcHandle,
  _Inout_   PCO_CALL_PARAMETERS CallParameters,
  _In_opt_  NDIS_HANDLE         ProtocolPartyContext,
  _Out_opt_ PNDIS_HANDLE        NdisPartyHandle
);
````


## -parameters




### -param NdisVcHandle [in]

Specifies the handle returned by a preceding call to 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>.


### -param CallParameters [in, out]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> in which the caller has
     specified the attributes for this connection, such as the address of the target for the call, latency,
     bandwidth, and quality of service if the network medium and address family supported by the call manager
     permits QoS specifications.


### -param ProtocolPartyContext [in, optional]

Optionally specifies a caller-supplied handle to a resident context area in which the client will
     maintain per-party state for the initial party on its multipoint VC. This parameter is <b>NULL</b> if the given
     VC does not represent a multipoint connection. For a multipoint VC, NDIS passes this handle back to the
     client's ProtocolCl<i>Xxx</i> functions in all subsequent calls that affect this particular party.


### -param NdisPartyHandle [out, optional]

Pointer to a caller-supplied variable, usually in the caller-allocated party context area, in
     which NDIS returns a handle representing the initial party to the multipoint connection if the request
     to set up an outgoing call is successful. If 
     <i>ProtocolPartyContext</i> is <b>NULL</b>, this variable, usually in the client's VC context area, also is set
     to <b>NULL</b> on completion of outgoing-call setup.


## -returns



When 
     <b>NdisClMakeCall</b> returns anything other than NDIS_STATUS_PENDING, the client should make an internal
     call to its 
     <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">
     ProtocolClMakeCallComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClMakeCallComplete</i> function when this operation is completed.




## -remarks



<b>NdisClMakeCall</b> sets up the attributes of a client-created VC for a client-initiated outgoing call.
    The client must set up the VC with 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> before it attempts to make
    an outgoing call.

A call to 
    <b>NdisClMakeCall</b> causes NDIS to forward this request to the 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function of the
    call manager with which the client shares the given 
    <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">NdisVcHandle</a>. The CM is
    responsible for validating the given data at 
    <i>CallParameters</i> . It can modify this client-supplied data while negotiating with relevant network
    components and can return different traffic parameters than the client originally gave to 
    <b>NdisClMakeCall</b>. The client's 
    <i>
    ProtocolClMakeCallComplete</i> function is responsible for accepting the modified call parameters if
    this occurs or for tearing down the call if the CM's proposed call parameters are unacceptable.

Consequently, the data at 
    <i>CallParameters</i> must remain available to the call manager at least for the duration of call setup.
    The client cannot free this buffer when 
    <b>NdisClMakeCall</b> returns NDIS_STATUS_PENDING. It must defer releasing this client-allocated resource
    until its 
    <i>ProtocolClMakeCallComplete</i> function is called.

If 
    <b>NdisClMakeCall</b> sets up a multipoint connection, the client is establishing the traffic parameters
    globally for the given VC, unless the underlying network medium supports per-party traffic
    parameters.

The client's 
    <i>ProtocolClMakeCallComplete</i> function should check the input 
    <i>Status</i> for NDIS_STATUS_SUCCESS before it uses any returned handle at 
    <i>NdisPartyHandle</i> . If the call manager fails the request to set up a call on a multipoint
    connection, the value of this client-supplied variable is invalid.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndiscmmakecallcomplete.md">NdisCmMakeCallComplete</a>



<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>



<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>



<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>



<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



<a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">ProtocolClMakeCallComplete</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



 

 


