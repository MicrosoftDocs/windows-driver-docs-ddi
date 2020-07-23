---
UID: NF:ndis.NdisCmNotifyCloseAddressFamily
title: NdisCmNotifyCloseAddressFamily function (ndis.h)
description: The NdisCmNotifyCloseAddressFamily function notifies NDIS that a call manager is unbinding from an underlying miniport adapter and that any associated CoNDIS clients should close the specified address family (AF).
old-location: netvista\ndiscmnotifycloseaddressfamily.htm
tech.root: netvista
ms.assetid: 1967f663-86ce-4e9d-9498-61951bdf4db0
ms.date: 05/02/2018
keywords: ["NdisCmNotifyCloseAddressFamily function"]
ms.keywords: NdisCmNotifyCloseAddressFamily, NdisCmNotifyCloseAddressFamily function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_91b51137-6a26-4b90-a83c-c06a9463bf97.xml, ndis/NdisCmNotifyCloseAddressFamily, netvista.ndiscmnotifycloseaddressfamily
f1_keywords:
 - "ndis/NdisCmNotifyCloseAddressFamily"
 - "NdisCmNotifyCloseAddressFamily"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCmNotifyCloseAddressFamily
targetos: Windows
req.typenames: 
---

# NdisCmNotifyCloseAddressFamily function


## -description


The 
  <b>NdisCmNotifyCloseAddressFamily</b> function notifies NDIS that a call manager is unbinding from an
  underlying miniport adapter and that any associated CoNDIS clients should close the specified address
  family (AF).


## -parameters




### -param NdisAfHandle [in]

An NDIS handle that identifies the AF that NDIS should close. NDIS supplied this handle to the
     call manager's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a> function.


## -returns



<b>NdisCmNotifyCloseAddressFamily</b> can return one of the following:

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
NDIS successfully closed the address family.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
NDIS is handling this request asynchronously, and it will call the call manager's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
       ProtocolCmNotifyCloseAfComplete</a> function when the close operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
NDIS failed the request for some NDIS or client driver-determined reason.

</td>
</tr>
</table>
 




## -remarks



Stand-alone CoNDIS call managers, which register as NDIS protocol drivers by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">
    NdisRegisterProtocolDriver</a> function, can call the 
    <b>NdisCmNotifyCloseAddressFamily</b> function. Miniport call managers (MCMs) instead call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmnotifycloseaddressfamily">
    NdisMCmNotifyCloseAddressFamily</a> function.

To close an AF for a binding, the stand-alone call manager should call 
    <b>NdisCmNotifyCloseAddressFamily</b> from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> function. NDIS then calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">
    ProtocolClNotifyCloseAf</a> function of the client that has the specified AF open.

If 
    <b>NdisCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls the call manager's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
    ProtocolCmNotifyCloseAfComplete</a> function after the client completes the AF close operation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmnotifycloseaddressfamily">
   NdisMCmNotifyCloseAddressFamily</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_notify_close_af">ProtocolClNotifyCloseAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_notify_close_af_complete">
   ProtocolCmNotifyCloseAfComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_open_af">ProtocolCmOpenAf</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>
 

 

