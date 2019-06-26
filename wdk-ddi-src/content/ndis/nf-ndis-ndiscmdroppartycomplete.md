---
UID: NF:ndis.NdisCmDropPartyComplete
title: NdisCmDropPartyComplete function (ndis.h)
description: NdisCmDropPartyComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.
old-location: netvista\ndiscmdroppartycomplete.htm
tech.root: netvista
ms.assetid: 5f4743f6-42b7-4cc0-8dd8-16230b30bb8a
ms.date: 05/02/2018
ms.keywords: NdisCmDropPartyComplete, NdisCmDropPartyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_d1773adc-25ef-4544-8ccf-70fe676a862d.xml, ndis/NdisCmDropPartyComplete, netvista.ndiscmdroppartycomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDropPartyComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDropPartyComplete (NDIS   5.1)) in Windows XP.
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
- NdisCmDropPartyComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCmDropPartyComplete function


## -description


<b>NdisCmDropPartyComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.


## -parameters




### -param Status [in]

Specifies the final status of the requested operation, either NDIS_STATUS_SUCCESS or any
     CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisPartyHandle [in]

Specifies the handle to the party that the client requested to be dropped. The call manager
     obtained this handle from the state area designated by 
     <i>CallMgrPartyContext</i> that was passed as an input parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_drop_party">
     ProtocolCmDropParty</a> function.


## -returns



None




## -remarks



A stand-alone call manager must call 
    <b>NdisCmDropPartyComplete</b> if its 
    <i>ProtocolCmDropParty</i> function previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisPartyHandle</i> . Neither NDIS nor the client, which initiated the pended drop-party operation with
    a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>, can release the
    resources they allocated to maintain per-party state until the CM's call to 
    <b>NdisCmDropPartyComplete</b> causes a call to that client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_drop_party_complete">
    ProtocolClDropPartyComplete</a> function.

If it passes NDIS_STATUS_SUCCESS for the 
    <i>Status</i>, the call manager should consider the 
    <i>NdisPartyHandle</i> invalid as soon as it calls 
    <b>NdisCmDropPartyComplete</b>. The CM can release (or reinitialize for reuse) any resources that it
    allocated to maintain state for this party when 
    <b>NdisCmDropPartyComplete</b> returns control.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDropPartyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDropPartyComplete</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdroppartycomplete">NdisMCmDropPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_drop_party_complete">ProtocolClDropPartyComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_drop_party">ProtocolCmDropParty</a>
 

 

