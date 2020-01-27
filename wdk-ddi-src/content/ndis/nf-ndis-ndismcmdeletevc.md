---
UID: NF:ndis.NdisMCmDeleteVc
title: NdisMCmDeleteVc function (ndis.h)
description: NdisMCmDeleteVc destroys a caller-created VC.
old-location: netvista\ndismcmdeletevc.htm
tech.root: netvista
ms.assetid: b55d0995-efd8-4a61-85e9-970559e21a88
ms.date: 05/02/2018
ms.keywords: NdisMCmDeleteVc, NdisMCmDeleteVc function [Network Drivers Starting with Windows Vista], condis_mcm_ref_a6a2bb4d-a82e-422f-b9f0-821519513cb4.xml, ndis/NdisMCmDeleteVc, netvista.ndismcmdeletevc
f1_keywords:
 - "ndis/NdisMCmDeleteVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeleteVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeleteVc (NDIS 5.1)) in   Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMCmDeleteVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmDeleteVc function


## -description


<b>NdisMCmDeleteVc</b> destroys a caller-created VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC to be deleted. The caller originally obtained this handle
     from 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>.


## -returns



<b>NdisMCmDeleteVc</b> can return one of the following:

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
</table>
 




## -remarks



When an MCM driver calls 
    <b>NdisMCmDeleteVc</b>, there must be no outstanding calls on the given VC and that VC must have been
    deactivated. To meet these requirements implies that the MCM driver has already called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a> with the given 
    <i>NdisVcHandle</i> successfully.

Only the driver that created a particular VC can delete that VC. A call to 
    <b>NdisMCmDeleteVc</b> causes NDIS to call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function of the
    client with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisMCmDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid. The MCM driver can release the resources it allocated to maintain
    state about the deleted VC or prepare them for reuse in a subsequent incoming-call notification after it
    calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a> function that the
    driver calls in the context of tearing down connections for outgoing and incoming calls.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeleteVc</b>. Stand-alone call managers and clients, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCoDeleteVc</b> instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_delete_vc">MiniportCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmcreatevc">NdisMCmCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdeactivatevc">NdisMCmDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

