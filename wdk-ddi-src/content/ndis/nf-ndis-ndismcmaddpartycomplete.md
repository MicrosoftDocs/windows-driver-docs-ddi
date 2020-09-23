---
UID: NF:ndis.NdisMCmAddPartyComplete
title: NdisMCmAddPartyComplete macro (ndis.h)
description: NdisMCmAddPartyComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.
old-location: netvista\ndismcmaddpartycomplete.htm
tech.root: netvista
ms.assetid: 5bbcd552-00c2-4085-8222-c514eb92e654
ms.date: 05/02/2018
keywords: ["NdisMCmAddPartyComplete macro"]
ms.keywords: NdisMCmAddPartyComplete, NdisMCmAddPartyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_929fb1d1-4d15-4d2d-be4b-a6845674f7e6.xml, ndis/NdisMCmAddPartyComplete, netvista.ndismcmaddpartycomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmAddPartyComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmAddPartyComplete (NDIS   5.1)) in Windows XP.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCmAddPartyComplete
 - ndis/NdisMCmAddPartyComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMCmAddPartyComplete
---

# NdisMCmAddPartyComplete macro


## -description

<b>NdisMCmAddPartyComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.

## -parameters

### -param _S_

Specifies the final status of the MCM driver's add-party operation, either NDIS_STATUS_SUCCESS or
     any NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING.

### -param _H_

Specifies the handle identifying the party. The MCM driver obtained this handle as input parameter
     to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function.

### -param _C_

Specifies the handle to a caller-allocated resident context area in which the MCM driver will
     maintain party-specific state information if the add-party operation succeeded. Otherwise, this
     parameter can be <b>NULL</b> because it is ignored by NDIS if 
     <i>Status</i> is anything other than NDIS_STATUS_SUCCESS.

### -param _P_

Pointer to a structure of type 
     <a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> that contains the call
     parameters, originally supplied by the client, for the party to be added.

## -remarks

If an MCM driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a> function returns
    NDIS_STATUS_PENDING, the driver must call 
    <b>NdisMCmAddPartyComplete</b> subsequently to notify the client and NDIS that its attempt to add a party
    on the multipoint VC has completed, whether successfully or with an MCM driver-determined error
    status.

The underlying network medium determines whether a client can specify per-party traffic parameters on
    a multipoint VC.

If the underlying network medium does not support per-party traffic parameters on multipoint VCs, an
    MCM driver can do one of the following whenever a client attempts to add a party with a specification at 
    <i>CallParameters</i> that does not match the already established traffic parameters for that VC:

<ul>
<li>
Reset the traffic parameters to those already established for the multipoint VC when it successfully
      adds the party on that VC.

</li>
<li>
Change the traffic parameters for every party already on the VC when it successfully adds the new
      party.

</li>
<li>
Reject the request to add a new party. (This alternative implicitly forces clients to set up their
      traffic parameters for a multipoint VC with 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a> and to specify the same
      traffic parameters at each subsequent call to 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a> for the given multipoint
      VC.)

</li>
</ul>
If the MCM driver sets 
    <i>Status</i> to NDIS_STATUS_SUCCESS, it must supply an explicit handle, which is usually a pointer to the
    driver-allocated per-party state area, as 
    <i>CallMgrPartyContext</i> when it calls 
    <b>NdisMCmAddPartyComplete</b>.

A call to 
    <b>NdisMCmAddPartyComplete</b> causes NDIS to call the client's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">
    ProtocolClAddPartyComplete</a> function.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmAddPartyComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmAddPartyComplete</b> instead.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscladdparty">NdisClAddParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmaddpartycomplete">NdisCmAddPartyComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdroppartycomplete">NdisMCmDropPartyComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_add_party_complete">ProtocolClAddPartyComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_add_party">ProtocolCmAddParty</a>