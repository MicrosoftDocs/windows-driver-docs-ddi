---
UID: NF:ndis.NdisClDropParty
title: NdisClDropParty function
author: windows-driver-content
description: NdisClDropParty drops a party from the client's multipoint VC.
old-location: netvista\ndiscldropparty.htm
old-project: netvista
ms.assetid: f5d04730-a7eb-4670-9b47-f8c52267aea8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisClDropParty, condis_client_ref_a86ff56b-e523-4d1b-a3ef-60ec953514c6.xml, NdisClDropParty function [Network Drivers Starting with Windows Vista], ndis/NdisClDropParty, netvista.ndiscldropparty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClDropParty (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClDropParty (NDIS 5.1)) in   Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisClDropParty
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisClDropParty function


## -description


<b>NdisClDropParty</b> drops a party from the client's multipoint VC.


## -syntax


````
NDIS_STATUS NdisClDropParty(
  _In_     NDIS_HANDLE NdisPartyHandle,
  _In_opt_ PVOID       Buffer,
  _In_opt_ UINT        Size
);
````


## -parameters




### -param NdisPartyHandle [in]

Specifies the handle identifying the party to be dropped on the multipoint connection. The client
     obtained this handle from a preceding call to 
     <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> or 
     <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.


### -param Buffer [in, optional]

Pointer to a caller-allocated buffer containing any data to be transmitted to close the multipoint
     connection of the party on the remote node. Depending on the underlying medium, this pointer can be
     <b>NULL</b>.


### -param Size [in, optional]

Specifies the size in bytes at 
     <i>Buffer</i>, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## -returns



When 
     <b>NdisClDropParty</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">
     ProtocolClDropPartyComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClDropPartyComplete</i> function when this operation is completed.




## -remarks



Clients usually call 
    <b>NdisClDropParty</b> in either of the following circumstances:

<ul>
<li>
From the 
      <a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">
      ProtocolClIncomingDropParty</a> function to remove the given party from a multipoint connection.

This occurs when a party on a remote node closes its connection with 
      <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>. When NDIS calls the
      local client's 
      <i>ProtocolClDropPartyComplete</i> function, it can release or reuse the context area at 
      <i>ProtocolPartyContext</i> in which the client was maintaining state about this party.

</li>
<li>
Before the client calls 
      <b>NdisClCloseCall</b> with the last party on a multipoint connection that the client originally set up
      with 
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.

For such a client-initiated close of its own multipoint call, the client must call 
      <b>NdisClDropParty</b> one or more times to drop every other remaining party on the multipoint VC.

</li>
</ul>
A client's call to 
    <b>NdisClDropParty</b> causes NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a> function of the
    call manager that shares the same 
    <i>NdisVcHandle</i> to the multipoint VC. The call manager is responsible for notifying its remote-node
    peer that the party connection has been or should be closed, depending on which client initiated the
    drop-party operation.

As a general guideline, a client must call 
    <b>NdisClDropParty</b> as many times as it called 
    <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> with a particular 
    <i>NdisVcHandle</i> obtained from 
    <b>NdisClMakeCall</b> 
    before it closes its multipoint connection with 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>. Since remote parties can
    initiate closes of their connections, thereby causing calls to the local client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">
    ProtocolClIncomingDropParty</a> function, the local client must keep track of the number of active
    parties on its multipoint VCs in order to know how many calls it must make to 
    <b>NdisClDropParty</b> before it can call 
    <b>NdisClCloseCall</b>.

However, the client is not required to pass 
    <b>NdisClCloseCall</b> the same 
    <i>NdisPartyHandle</i> returned by 
    <b>NdisClMakeCall</b> when the client originally set up its multipoint connection. The client can release
    parties on its multipoint VC in any order, as long as it releases every 
    <i>NdisPartyHandle</i> returned by 
    <b>NdisClAddParty</b> or 
    <b>NdisClMakeCall</b> in its calls to 
    <b>NdisClDropParty</b>, followed by a final call with the last party handle to 
    <b>NdisClCloseCall</b> for the same multipoint VC. After the client has closed its multipoint call, it can
    release the VC that it originally created with 
    <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>.

The caller of 
    <b>NdisClDropParty</b> should consider the input 
    <i>NdisPartyHandle</i> invalid as soon as it makes this call. If it stored this handle in the party
    context area it allocated, the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">
    ProtocolClDropPartyComplete</a> function should reset the handle variable to <b>NULL</b> if it reinitializes
    its per-party context area for reuse when the party has been dropped.




## -see-also

<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>



<a href="..\ndis\nc-ndis-protocol_cl_drop_party_complete.md">ProtocolClDropPartyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">ProtocolClIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClDropParty function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

