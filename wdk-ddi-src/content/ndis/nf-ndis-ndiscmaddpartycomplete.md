---
UID: NF:ndis.NdisCmAddPartyComplete
title: NdisCmAddPartyComplete function
author: windows-driver-content
description: NdisCmAddPartyComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to add a party on an established multipoint VC.
old-location: netvista\ndiscmaddpartycomplete.htm
old-project: netvista
ms.assetid: 00833038-1fff-4103-9508-07cb8cbfa846
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisCmAddPartyComplete, NdisCmAddPartyComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_5a60a49b-5bca-48b4-9659-af4e8bdfd032.xml, ndis/NdisCmAddPartyComplete, netvista.ndiscmaddpartycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	NdisCmAddPartyComplete
product: Windows
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
     <a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a> function.


### -param CallMgrPartyContext [in, optional]

Specifies the handle to a caller-allocated resident context area in which the call manager will
     maintain party-specific state information if the add-party operation succeeded. Otherwise, this
     parameter can be <b>NULL</b> because it is ignored.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that contains the call
     parameters, originally supplied by the client, for the party to be added.


## -returns



None




## -remarks



If a stand-alone call manager's 
    <a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a> function returns
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
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a> and to specify the same
      traffic parameters at each subsequent call to 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a> for the given multipoint
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
    <a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">
    ProtocolClAddPartyComplete</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmAddPartyComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmAddPartyComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562798">NdisMCmAddPartyComplete</a>



<a href="https://msdn.microsoft.com/ea3ebbe9-fd94-44b8-8801-639d099c5158">ProtocolClAddPartyComplete</a>



<a href="https://msdn.microsoft.com/06aa5ff6-974c-43dd-8395-bc1a1a8421d5">ProtocolCmAddParty</a>
 

 

