---
UID: NF:ndis.NdisCmDropPartyComplete
title: NdisCmDropPartyComplete function
author: windows-driver-content
description: NdisCmDropPartyComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.
old-location: netvista\ndiscmdroppartycomplete.htm
old-project: netvista
ms.assetid: 5f4743f6-42b7-4cc0-8dd8-16230b30bb8a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisCmDropPartyComplete, netvista.ndiscmdroppartycomplete, ndis/NdisCmDropPartyComplete, NdisCmDropPartyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_d1773adc-25ef-4544-8ccf-70fe676a862d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCmDropPartyComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmDropPartyComplete function


## -description


<b>NdisCmDropPartyComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.


## -syntax


````
VOID NdisCmDropPartyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisPartyHandle
);
````


## -parameters




### -param Status [in]

Specifies the final status of the requested operation, either NDIS_STATUS_SUCCESS or any
     CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisPartyHandle [in]

Specifies the handle to the party that the client requested to be dropped. The call manager
     obtained this handle from the state area designated by 
     <i>CallMgrPartyContext</i> that was passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">
     ProtocolCmDropParty</a> function.


## -returns


None



## -remarks


A stand-alone call manager must call 
    <b>NdisCmDropPartyComplete</b> if its 
    <i>ProtocolCmDropParty</i> function previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisPartyHandle</i> . Neither NDIS nor the client, which initiated the pended drop-party operation with
    a call to 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>, can release the
    resources they allocated to maintain per-party state until the CM's call to 
    <b>NdisCmDropPartyComplete</b> causes a call to that client's 
    <a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">
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

<a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">ProtocolClDropPartyComplete</a>

<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>

<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>

<a href="..\ndis\nf-ndis-ndismcmdroppartycomplete.md">NdisMCmDropPartyComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmDropPartyComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

