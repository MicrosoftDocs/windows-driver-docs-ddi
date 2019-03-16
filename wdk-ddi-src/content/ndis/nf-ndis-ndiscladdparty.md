---
UID: NF:ndis.NdisClAddParty
title: NdisClAddParty function (ndis.h)
description: NdisClAddParty adds a party on the client's multipoint VC.
old-location: netvista\ndiscladdparty.htm
tech.root: netvista
ms.assetid: e48357b2-52dc-48af-aeb1-8d84ea107579
ms.date: 05/02/2018
ms.keywords: NdisClAddParty, NdisClAddParty function [Network Drivers Starting with Windows Vista], condis_client_ref_90d23e8e-f3a5-4a19-9eeb-b68a28f7f915.xml, ndis/NdisClAddParty, netvista.ndiscladdparty
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClAddParty function


## -description


<b>NdisClAddParty</b> adds a party on the client's multipoint VC.


## -parameters




### -param NdisVcHandle [in]

Pointer to the VC handle returned by 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>.


### -param ProtocolPartyContext [in]

Specifies the handle to a caller-allocated resident context area in which the client will maintain
     per-party state if its call succeeds.


### -param CallParameters [in, out]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> in which the caller has
     specified the addressing information for the party to be added on its multipoint VC.


### -param NdisPartyHandle [out]

Pointer to a variable to be set by NDIS if the add-party operation succeeds.


## -returns



When 
     <b>NdisClAddParty</b> returns anything other than NDIS_STATUS_PENDING, the client should make an internal
     call to its 
     <a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">
     ProtocolClAddPartyComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClAddPartyComplete</i> function when this operation is completed.




## -remarks



Before it calls 
    <b>NdisClAddParty</b>, a client must set up a multipoint connection on its VC with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>, as well as allocating and
    initializing its context area for the party to be added. Clients commonly pass a pointer to such a
    context area as the 
    <i>ProtocolPartyContext</i> and a pointer to a variable within that context area as the 
    <i>NdisPartyHandle</i> parameters when they call 
    <b>NdisClAddParty</b>.

A call to 
    <b>NdisClAddParty</b> causes NDIS to forward this request to the 
    <a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a> function of the
    call manager with which the client shares the given 
    <i>NdisVcHandle</i> . The call manager either returns an error status immediately or, more commonly,
    NDIS_STATUS_PENDING if it attempts to satisfy this request. If its attempt is rejected on the remote
    endpoint or by the underlying miniport driver, the call manager returns a final error status, such as
    NDIS_STATUS_FAILURE, when it calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561651">NdisCmAddPartyComplete</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562798">NdisMCmAddPartyComplete</a>. The
    client's 
    <a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">
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
    <a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561651">NdisCmAddPartyComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561716">NdisCoOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562798">NdisMCmAddPartyComplete</a>



<a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">ProtocolClAddPartyComplete</a>



<a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a>
 

 

