---
UID: NF:ndis.NdisClAddParty
title: NdisClAddParty function (ndis.h)
description: NdisClAddParty adds a party on the client's multipoint VC.
old-location: netvista\ndiscladdparty.htm
tech.root: netvista
ms.assetid: e48357b2-52dc-48af-aeb1-8d84ea107579
ms.date: 05/02/2018
keywords: ["NdisClAddParty function"]
ms.keywords: NdisClAddParty, NdisClAddParty function [Network Drivers Starting with Windows Vista], condis_client_ref_90d23e8e-f3a5-4a19-9eeb-b68a28f7f915.xml, ndis/NdisClAddParty, netvista.ndiscladdparty
f1_keywords:
 - "ndis/NdisClAddParty"
 - "NdisClAddParty"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClAddParty (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClAddParty (NDIS 5.1)) in   Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisClAddParty
targetos: Windows
req.typenames: 
---

# NdisClAddParty function


## -description


<b>NdisClAddParty</b> adds a party on the client's multipoint VC.


## -parameters




### -param NdisVcHandle 
[in]
Pointer to the VC handle returned by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>.


### -param ProtocolPartyContext 
[in]
Specifies the handle to a caller-allocated resident context area in which the client will maintain
     per-party state if its call succeeds.


### -param CallParameters 
[in, out]
Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> in which the caller has
     specified the addressing information for the party to be added on its multipoint VC.


### -param NdisPartyHandle 
[out]
Pointer to a variable to be set by NDIS if the add-party operation succeeds.


## -returns



When 
     <b>NdisClAddParty</b> returns anything other than NDIS_STATUS_PENDING, the client should make an internal
     call to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
     ProtocolClAddPartyComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClAddPartyComplete</i> function when this operation is completed.




## -remarks



Before it calls 
    <b>NdisClAddParty</b>, a client must set up a multipoint connection on its VC with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>, as well as allocating and
    initializing its context area for the party to be added. Clients commonly pass a pointer to such a
    context area as the 
    <i>ProtocolPartyContext</i> and a pointer to a variable within that context area as the 
    <i>NdisPartyHandle</i> parameters when they call 
    <b>NdisClAddParty</b>.

A call to 
    <b>NdisClAddParty</b> causes NDIS to forward this request to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function of the
    call manager with which the client shares the given 
    <i>NdisVcHandle</i> . The call manager either returns an error status immediately or, more commonly,
    NDIS_STATUS_PENDING if it attempts to satisfy this request. If its attempt is rejected on the remote
    endpoint or by the underlying miniport driver, the call manager returns a final error status, such as
    NDIS_STATUS_FAILURE, when it calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmaddpartycomplete">NdisCmAddPartyComplete</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmaddpartycomplete">NdisMCmAddPartyComplete</a>. The
    client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
    ProtocolClAddPartyComplete</a> function should check the input 
    <i>Status</i> argument for NDIS_STATUS_SUCCESS before proceeding further.

The underlying network medium determines whether a client can specify per-party traffic parameters on
    a multipoint VC.

If the underlying network medium does not support per-party traffic parameters on multipoint VCs, a
    call manager can do one of the following whenever a client attempts to add a party with a specification
    at 
    <i>CallParameters</i> that does not match the already established traffic parameters for that VC:

<ul>
<li>
Reject the request to add a new party.

</li>
<li>
Reset the traffic parameters to those already established for the multipoint VC when it successfully
      adds the party on that VC.

</li>
<li>
Change the traffic parameters for every party already on the VC when it successfully adds the new
      party.

</li>
</ul>
If the add-party operation succeeds, the variable at 
    <i>NdisPartyHandle</i> has been set by NDIS to a valid handle shared among NDIS, the client, and the call
    manager. The client must treat this NDIS-supplied handle as an opaque variable to be passed, unmodified
    and uninterpreted, in subsequent calls to 
    <b>NdisCl/Co<i>Xxx</i></b> functions concerning the newly added party.

In turn, NDIS passes the client-supplied 
    <i>ProtocolPartyContext</i> handle in subsequent calls to the client's ProtocolCl<i>Xxx</i> functions that concern this newly added party, including the call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
    ProtocolClAddPartyComplete</a>.

Whether a multipoint call permits transfers in both directions and/or per-party transfers with
    per-party traffic parameters depends on the medium of the underlying miniport driver to which the client
    is bound. The 
    <i>NdisPartyHandle</i> represents only the specific party added by a successful call to 
    <b>NdisClAddParty</b>, rather than the multipoint VC. Consequently, the client can use its 
    <i>ProtocolPartyContext</i> area only for subsequent party-specific call-management requests. For data
    transfers over network media that do not support per-party transfers or traffic parameters, the client
    must use the 
    <i>NdisVcHandle</i> instead.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmaddpartycomplete">NdisCmAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequestcomplete">NdisCoOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmaddpartycomplete">NdisMCmAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">ProtocolClAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>
 

 

