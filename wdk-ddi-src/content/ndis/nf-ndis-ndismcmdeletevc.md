---
UID: NF:ndis.NdisMCmDeleteVc
title: NdisMCmDeleteVc function
author: windows-driver-content
description: NdisMCmDeleteVc destroys a caller-created VC.
old-location: netvista\ndismcmdeletevc.htm
old-project: netvista
ms.assetid: b55d0995-efd8-4a61-85e9-970559e21a88
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCmDeleteVc, NdisMCmDeleteVc function [Network Drivers Starting with Windows Vista], condis_mcm_ref_a6a2bb4d-a82e-422f-b9f0-821519513cb4.xml, ndis/NdisMCmDeleteVc, netvista.ndismcmdeletevc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	NdisMCmDeleteVc
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDeleteVc function


## -description


<b>NdisMCmDeleteVc</b> destroys a caller-created VC.


## -parameters




### -param NdisVcHandle [in]

Specifies the handle identifying the VC to be deleted. The caller originally obtained this handle
     from 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a> with the given 
    <i>NdisVcHandle</i> successfully.

Only the driver that created a particular VC can delete that VC. A call to 
    <b>NdisMCmDeleteVc</b> causes NDIS to call the 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function of the
    client with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisMCmDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid. The MCM driver can release the resources it allocated to maintain
    state about the deleted VC or prepare them for reuse in a subsequent incoming-call notification after it
    calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a> function that the
    driver calls in the context of tearing down connections for outgoing and incoming calls.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeleteVc</b>. Stand-alone call managers and clients, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCoDeleteVc</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4">MiniportCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561698">NdisCoDeleteVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562812">NdisMCmCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562818">NdisMCmDeactivateVc</a>



<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDeleteVc function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
