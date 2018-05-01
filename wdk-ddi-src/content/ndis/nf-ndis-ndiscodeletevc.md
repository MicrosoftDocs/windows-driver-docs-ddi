---
UID: NF:ndis.NdisCoDeleteVc
title: NdisCoDeleteVc function
author: windows-driver-content
description: NdisCoDeleteVc destroys a caller-created VC.
old-location: netvista\ndiscodeletevc.htm
old-project: netvista
ms.assetid: 31e88a5b-d97c-482a-aab0-dd987b15d657
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisCoDeleteVc, NdisCoDeleteVc function [Network Drivers Starting with Windows Vista], condis_protocol_ref_19f96afa-aa63-44e4-817a-8b701c6d12c6.xml, ndis/NdisCoDeleteVc, netvista.ndiscodeletevc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCoDeleteVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCoDeleteVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Connection_Function
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
-	NdisCoDeleteVc
product: Windows
targetos: Windows
req.typenames: 
---

# NdisCoDeleteVc function


## -description


<b>NdisCoDeleteVc</b> destroys a caller-created VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC to be deleted. The caller originally obtained this handle
     from 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>.


## -returns



<b>NdisCoDeleteVc</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS deleted the VC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The VC is still active, so it could not be deleted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_CLOSING</b></dt>
</dl>
</td>
<td width="60%">
This call is redundant, but deactivation on the given VC is still pending.

</td>
</tr>
</table>
 




## -remarks



When a protocol calls 
    <b>NdisCoDeleteVc</b>, there must be no outstanding calls on the given VC and that VC already has been
    deactivated. To meet these requirements implies that the following conditions hold:

<ul>
<li>
If the call tear-down was initiated by a local client, that client has already called 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a> with the given 
      <i>NdisVcHandle</i> and its close-call request has completed successfully.

</li>
<li>
If the call tear-down was initiated by a remote client, the stand-alone call manager has already
      called 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a> with the given 
      <i>NdisVcHandle</i> and its deactivation request has completed successfully.

</li>
</ul>
Only the protocol that created a particular VC can delete that VC. A call to 
    <b>NdisCoDeleteVc</b> causes NDIS to call both the underlying miniport driver's 
    <a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a> function and the 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function of the
    client or call manager with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisCoDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid.

Stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCoDeleteVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a> instead.




## -see-also




<a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561657">NdisCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562819">NdisMCmDeleteVc</a>



<a href="https://msdn.microsoft.com/a7ba1ab2-04c9-45b5-a184-e1ad1448561a">ProtocolClCloseCallComplete</a>



<a href="https://msdn.microsoft.com/01c7d887-eb54-47c3-98f0-bc567b60fb4b">ProtocolClIncomingCloseCall</a>



<a href="https://msdn.microsoft.com/b5307e1b-3905-4e43-a0b0-0068ba18ef0d">ProtocolCmCloseCall</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

