---
UID: NF:ndis.NdisCmAddPartyComplete
title: NdisCmAddPartyComplete function (ndis.h)
description: NdisCmAddPartyComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.
old-location: netvista\ndiscmaddpartycomplete.htm
tech.root: netvista
ms.assetid: 00833038-1fff-4103-9508-07cb8cbfa846
ms.date: 05/02/2018
keywords: ["NdisCmAddPartyComplete function"]
ms.keywords: NdisCmAddPartyComplete, NdisCmAddPartyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_5a60a49b-5bca-48b4-9659-af4e8bdfd032.xml, ndis/NdisCmAddPartyComplete, netvista.ndiscmaddpartycomplete
f1_keywords:
 - "ndis/NdisCmAddPartyComplete"
 - "NdisCmAddPartyComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmAddPartyComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmAddPartyComplete (NDIS   5.1)) in Windows XP.
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
- NdisCmAddPartyComplete
targetos: Windows
req.typenames: 
---

# NdisCmAddPartyComplete function


## -description


<b>NdisCmAddPartyComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.


## -parameters




### -param Status [in]

Specifies the final status of the call manager's add-party operation, either NDIS_STATUS_SUCCESS
     or any NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisPartyHandle [in]

Specifies the handle identifying the party. This handle was input to the call manager's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.


### -param CallMgrPartyContext [in, optional]

Specifies the handle to a caller-allocated resident context area in which the call manager will
     maintain party-specific state information if the add-party operation succeeded. Otherwise, this
     parameter can be <b>NULL</b> because it is ignored.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that contains the call
     parameters, originally supplied by the client, for the party to be added.


## -remarks



If a stand-alone call manager's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function returns
    NDIS_STATUS_PENDING, the CM subsequently must call 
    <b>NdisCmAddPartyComplete</b> to notify the client and NDIS that its attempt to add a party on the
    multipoint VC has completed, whether successfully or with an error.

If the client passed in traffic parameters at 
    <i>CallParameters</i> that did not match those already established for the multipoint VC, the designer of
    the call manager must determine how to handle this condition, subject to any constraints imposed by the
    network medium. Possibilities include the following:

<ul>
<li>
Set up the per-party traffic parameters if the underlying network medium supports this feature on
      multipoint VCs.

</li>
<li>
Reset the client-supplied traffic parameters to those established for the VC when the original
      outgoing call was made before the CM calls 
      <b>NdisCmAddPartyComplete</b> with NDIS_STATUS_SUCCESS as the 
      <i>Status</i> .

</li>
<li>
Change the traffic parameters for the VC and, for every party currently connected on it, to the
      client-supplied values before the CM calls 
      <b>NdisCmAddPartyComplete</b> with NDIS_STATUS_SUCCESS as the 
      <i>Status</i> .

</li>
<li>
Fail the client's attempt to add a party. (This alternative implicitly forces clients to set up
      their traffic parameters for a multipoint VC with 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a> and to specify the same
      traffic parameters at each subsequent call to 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a> for the given multipoint
      VC.)

</li>
</ul>
For some connection-oriented media , traffic parameters are per-VC in nature and, consequently,
    identical for all parties on a multipoint VC.

If the CM sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, it must supply an explicit handle, which is usually a pointer to the
    CM-allocated per-party state area, as 
    <i>CallMgrPartyContext</i> when it calls 
    <b>NdisCmAddPartyComplete</b>.

A call to 
    <b>NdisCmAddPartyComplete</b> causes NDIS to call the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
    ProtocolClAddPartyComplete</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmAddPartyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmAddPartyComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmaddpartycomplete">NdisMCmAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">ProtocolClAddPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>
 

 

