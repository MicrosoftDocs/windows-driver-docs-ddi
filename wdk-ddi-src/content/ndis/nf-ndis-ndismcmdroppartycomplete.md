---
UID: NF:ndis.NdisMCmDropPartyComplete
title: NdisMCmDropPartyComplete macro
author: windows-driver-content
description: NdisMCmDropPartyComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.
old-location: netvista\ndismcmdroppartycomplete.htm
old-project: netvista
ms.assetid: ba0e11d9-3bb1-412c-9b33-9362d774adee
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndismcmdroppartycomplete, NdisMCmDropPartyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_61bf04f0-c6cd-445f-8e4a-512884b96902.xml, NdisMCmDropPartyComplete, ndis/NdisMCmDropPartyComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisMCmDropPartyComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDropPartyComplete macro


## -description


<b>NdisMCmDropPartyComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to remove a party from a multipoint VC.


## -syntax


````
VOID NdisMCmDropPartyComplete(
  [in] NDIS_STATUS Status,
  [in] NDIS_HANDLE NdisPartyHandle
);
````


## -parameters




### -param _S_

TBD


### -param _H_

TBD






#### - Status [in]

Specifies the final status of the requested operation, either NDIS_STATUS_SUCCESS or any
     caller-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


#### - NdisPartyHandle [in]

Specifies the handle to the party that the client requested be dropped. The MCM driver obtained
     this handle from its per-party state area designated by 
     <i>CallMgrPartyContext</i> that was passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">
     ProtocolCmDropParty</a> function.


## -remarks



An MCM driver must call 
    <b>NdisMCmDropPartyComplete</b> if its 
    <i>ProtocolCmDropParty</i> function previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisPartyHandle</i> . Neither NDIS nor the client, which initiated the pended drop-party operation with
    a call to 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>, can release the
    resources they allocated to maintain per-party state until the MCM driver's call to 
    <b>NdisMCmDropPartyComplete</b> causes a call to that client's 
    <a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">
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

<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>



<a href="..\ndis\nf-ndis-ndiscmdroppartycomplete.md">NdisCmDropPartyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">ProtocolClDropPartyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDropPartyComplete macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

