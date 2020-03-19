---
UID: NF:ndis.NdisUnbindAdapter
title: NdisUnbindAdapter function (ndis.h)
description: Protocol drivers call the NdisUnbindAdapter function to request NDIS to close a binding to an underlying miniport adapter.
old-location: netvista\ndisunbindadapter.htm
tech.root: netvista
ms.assetid: 47aacc23-f7d1-4c14-9541-3207debef327
ms.date: 05/02/2018
keywords: ["NdisUnbindAdapter function"]
ms.keywords: NdisUnbindAdapter, NdisUnbindAdapter function [Network Drivers Starting with Windows Vista], ndis/NdisUnbindAdapter, netvista.ndisunbindadapter, protocol_ndis_functions_ref_99324c18-23da-4ed1-9ccc-ab73ac342c50.xml
f1_keywords:
 - "ndis/NdisUnbindAdapter"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- NdisUnbindAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisUnbindAdapter function


## -description


Protocol drivers call the 
  <b>NdisUnbindAdapter</b> function to request NDIS to close a binding to an underlying miniport
  adapter.


## -parameters




### -param NdisBindingHandle [in]

A handle that the protocol driver obtained from a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function. The handle
     identifies the binding to close.


## -returns



<b>NdisUnbindAdapter</b> returns one of the following status values:

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
<b>NdisUnbindAdapter</b> successfully initiated the unbind operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisUnbindAdapter</b> failed due to insufficient resources.

</td>
</tr>
</table>
 




## -remarks



Protocol drivers call 
    <b>NdisUnbindAdapter</b> outside the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> functions.
    NDIS schedules a work item to call the protocol driver's 
    <i>ProtocolUnbindAdapterEx</i> function and returns immediately.

Before the call to 
    <b>NdisUnbindAdapter</b> returns, NDIS can already have closed the binding. Therefore, after the call
    returns, the caller must not assume that the handle it passed to the 
    <i>NdisBindingHandle</i> parameter is still valid.

<div class="alert"><b>Note</b>  NDIS might not call 
    <i>ProtocolUnbindAdapterEx</i> even if 
    <b>NdisUnbindAdapter</b> returns NDIS_STATUS_SUCCESS.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

