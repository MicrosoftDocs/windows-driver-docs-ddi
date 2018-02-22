---
UID: NF:ndis.NdisMCmAddPartyComplete
title: NdisMCmAddPartyComplete macro
author: windows-driver-content
description: NdisMCmAddPartyComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.
old-location: netvista\ndismcmaddpartycomplete.htm
old-project: netvista
ms.assetid: 5bbcd552-00c2-4085-8222-c514eb92e654
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: condis_mcm_ref_929fb1d1-4d15-4d2d-be4b-a6845674f7e6.xml, netvista.ndismcmaddpartycomplete, ndis/NdisMCmAddPartyComplete, NdisMCmAddPartyComplete, NdisMCmAddPartyComplete macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	NdisMCmAddPartyComplete
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMCmAddPartyComplete macro


## -description


<b>NdisMCmAddPartyComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.


## -syntax


````
VOID NdisMCmAddPartyComplete(
  [in]           NDIS_STATUS         Status,
  [in]           NDIS_HANDLE         NdisPartyHandle,
  [in, optional] NDIS_HANDLE         CallMgrPartyContext,
  [in]           PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters




### -param _S_

TBD


### -param _H_

TBD


### -param _C_

TBD


### -param _P_

TBD






#### - Status [in]

Specifies the final status of the MCM driver's add-party operation, either NDIS_STATUS_SUCCESS or
     any NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING.


#### - NdisPartyHandle [in]

Specifies the handle identifying the party. The MCM driver obtained this handle as input parameter
     to its 
     <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function.


#### - CallMgrPartyContext [in, optional]

Specifies the handle to a caller-allocated resident context area in which the MCM driver will
     maintain party-specific state information if the add-party operation succeeded. Otherwise, this
     parameter can be <b>NULL</b> because it is ignored by NDIS if 
     <i>Status</i> is anything other than NDIS_STATUS_SUCCESS.


#### - CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that contains the call
     parameters, originally supplied by the client, for the party to be added.


## -remarks



If an MCM driver's 
    <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function returns
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
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> and to specify the same
      traffic parameters at each subsequent call to 
      <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> for the given multipoint
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
    <a href="..\ndis\nc-ndis-protocol_cl_add_party_complete.md">
    ProtocolClAddPartyComplete</a> function.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmAddPartyComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmAddPartyComplete</b> instead.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndiscmaddpartycomplete.md">NdisCmAddPartyComplete</a>



<a href="..\ndis\nf-ndis-ndismcmdroppartycomplete.md">NdisMCmDropPartyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a>



<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>



<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>



<a href="..\ndis\nc-ndis-protocol_cl_add_party_complete.md">ProtocolClAddPartyComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmAddPartyComplete macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

