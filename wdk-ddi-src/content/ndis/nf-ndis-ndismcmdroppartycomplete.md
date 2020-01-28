---
UID: NF:ndis.NdisMCmDropPartyComplete
title: NdisMCmDropPartyComplete macro (ndis.h)
description: NdisMCmDropPartyComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.
old-location: netvista\ndismcmdroppartycomplete.htm
tech.root: netvista
ms.assetid: ba0e11d9-3bb1-412c-9b33-9362d774adee
ms.date: 05/02/2018
ms.keywords: NdisMCmDropPartyComplete, NdisMCmDropPartyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_61bf04f0-c6cd-445f-8e4a-512884b96902.xml, ndis/NdisMCmDropPartyComplete, netvista.ndismcmdroppartycomplete
f1_keywords:
 - "ndis/NdisMCmDropPartyComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDropPartyComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDropPartyComplete (NDIS   5.1)) in Windows XP.
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
- NdisMCmDropPartyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDropPartyComplete macro


## -description


<b>NdisMCmDropPartyComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.


## -parameters




### -param _S_

Specifies the final status of the requested operation, either NDIS_STATUS_SUCCESS or any
     caller-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.

### -param _H_

Specifies the handle to the party that the client requested be dropped. The MCM driver obtained
     this handle from its per-party state area designated by 
     <i>CallMgrPartyContext</i> that was passed as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_drop_party">
     ProtocolCmDropParty</a> function.

## -remarks



An MCM driver must call 
    <b>NdisMCmDropPartyComplete</b> if its 
    <i>ProtocolCmDropParty</i> function previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisPartyHandle</i> . Neither NDIS nor the client, which initiated the pended drop-party operation with
    a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>, can release the
    resources they allocated to maintain per-party state until the MCM driver's call to 
    <b>NdisMCmDropPartyComplete</b> causes a call to that client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_drop_party_complete">
    ProtocolClDropPartyComplete</a> function.

If it passes NDIS_STATUS_SUCCESS for the 
    <i>Status</i>, the MCM driver must consider the 
    <i>NdisPartyHandle</i> invalid when 
    <b>NdisMCmDropPartyComplete</b> returns control. The MCM driver can release (or reinitialize for reuse)
    any resources that it allocated to maintain state for this party after 
    <b>NdisMCmDropPartyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDropPartyComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDropPartyComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdroppartycomplete">NdisCmDropPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_drop_party_complete">ProtocolClDropPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_drop_party">ProtocolCmDropParty</a>
 

 

