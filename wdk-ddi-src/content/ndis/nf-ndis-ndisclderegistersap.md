---
UID: NF:ndis.NdisClDeregisterSap
title: NdisClDeregisterSap function (ndis.h)
description: NdisClDeregisterSap releases a previously registered SAP.
old-location: netvista\ndisclderegistersap.htm
tech.root: netvista
ms.assetid: ee3eb668-04f5-4731-b0bd-5cc8a9d4407f
ms.date: 05/02/2018
ms.keywords: NdisClDeregisterSap, NdisClDeregisterSap function [Network Drivers Starting with Windows Vista], condis_client_ref_44c25719-9fbb-496b-97f6-f897cfe2b346.xml, ndis/NdisClDeregisterSap, netvista.ndisclderegistersap
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClDeregisterSap (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClDeregisterSap (NDIS   5.1)) in Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisClDeregisterSap
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClDeregisterSap function


## -description


<b>NdisClDeregisterSap</b> releases a previously registered SAP.


## -parameters




### -param NdisSapHandle [in]

Specifies the handle returned by 
     <b>NdisClRegisterSap</b>.


## -returns



<b>NdisClDeregisterSap</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The call manager's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_deregister_sap">
       ProtocolCmDeregisterSap</a> function has been called to complete the requested operation. NDIS calls
       the client's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
       ProtocolClDeregisterSapComplete</a> function when this operation is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The SAP already is being closed, so this is a redundant call. If 
       <b>NdisClRegisterSap</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
       internal call to its 
       <i>ProtocolClRegisterSapComplete</i> function.

</td>
</tr>
</table>
 




## -remarks



<b>NdisClDeregisterSap</b> releases a SAP on which the client previously registered itself to receive
    incoming calls with 
    <b>NdisClRegisterSap</b>.

The client should consider the given 
    <i>NdisSapHandle</i> invalid as soon as it calls 
    <b>NdisClDeregisterSap</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndiscmregistersapcomplete">NdisCmRegisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cl_deregister_sap_complete">
   ProtocolClDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_cm_deregister_sap">ProtocolCmDeregisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

