---
UID: NF:ndis.NdisCoDeleteVc
title: NdisCoDeleteVc function (ndis.h)
description: NdisCoDeleteVc destroys a caller-created VC.
old-location: netvista\ndiscodeletevc.htm
tech.root: netvista
ms.assetid: 31e88a5b-d97c-482a-aab0-dd987b15d657
ms.date: 05/02/2018
ms.keywords: NdisCoDeleteVc, NdisCoDeleteVc function [Network Drivers Starting with Windows Vista], condis_protocol_ref_19f96afa-aa63-44e4-817a-8b701c6d12c6.xml, ndis/NdisCoDeleteVc, netvista.ndiscodeletevc
ms.topic: function
f1_keywords:
 - "ndis/NdisCoDeleteVc"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCoDeleteVc
product:
- Windows
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>.


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
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a> with the given 
      <i>NdisVcHandle</i> and its close-call request has completed successfully.

</li>
<li>
If the call tear-down was initiated by a remote client, the stand-alone call manager has already
      called 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a> with the given 
      <i>NdisVcHandle</i> and its deactivation request has completed successfully.

</li>
</ul>
Only the protocol that created a particular VC can delete that VC. A call to 
    <b>NdisCoDeleteVc</b> causes NDIS to call both the underlying miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a> function and the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function of the
    client or call manager with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisCoDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid.

Stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCoDeleteVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcmdeletevc">NdisMCmDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_close_call_complete">ProtocolClCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

