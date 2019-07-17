---
UID: NF:ndis.MINIPORT_SYNCHRONOUS_OID_REQUEST
title: MINIPORT_SYNCHRONOUS_OID_REQUEST function (ndis.h)
description: NDIS calls a miniport driver's MiniportSynchronousOidRequest callback function to issue a Synchronous OID request.
old-location: netvista\miniport_synchronous_oid_request.htm
tech.root: netvista
ms.assetid: 0DDF9CF8-91F6-4D7C-A8E8-FC425BF155CB
ms.date: 05/02/2018
ms.keywords: MINIPORT_SYNCHRONOUS_OID_REQUEST, MiniportSynchronousOidRequest, MiniportSynchronousOidRequest function [Network Drivers Starting with Windows Vista], ndis/MiniportSynchronousOidRequest, netvista.miniport_synchronous_oid_request
ms.topic: function
f1_keywords:
 - "ndis/MiniportSynchronousOidRequest"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- MiniportSynchronousOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_SYNCHRONOUS_OID_REQUEST function


## -description


NDIS calls a miniport driver's <i>MiniportSynchronousOidRequest</i> callback function to issue a Synchronous OID request.


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param OidRequest [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure that is provided.


## -returns



<i>MiniportSynchronousOidRequest</i> can return one of the following status values:

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
The miniport driver set or obtained the data as requested.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The request that 
       <i>OidRequest</i> specified was invalid or not recognized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The request that 
       <i>OidRequest</i> specified was recognized, but the miniport driver does not support it.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The buffer that 
       <i>OidRequest</i> supplies was too small to hold the requested data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST structure at 
       <i>OidRequest</i> is incorrect for the specified OID_<i>Xxx</i> code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
One or more of the parameters that were specified for the request at 
       <i>OidRequest</i> were invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INDICATION_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver will provide an OID completion status with a subsequent status indication. A
       miniport driver cannot return NDIS_STATUS_INDICATION_REQUIRED unless the particular OID allows it. To
       determine if this status is allowed, see the OID reference page. For more information about
       NDIS_STATUS_INDICATION_REQUIRED, see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> and 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
After calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_device_pnp_event_notify">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS called the driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function. If the
       driver received any OID requests before NDIS calls 
       <i>MiniportHaltEx</i>, it should immediately complete such requests with a status value of
       NDIS_STATUS_NOT_ACCEPTED.

Miniport drivers are not always required to return NDIS_STATUS_NOT_ACCEPTED for all OIDs after a surprise removal, but doing so helps explain why the call failed.

</td>
</tr>
</table>
 




## -remarks



<i>MiniportSynchronousOidRequest</i> is an optional function. A miniport driver registers this function if it handles Synchronous OID requests. The driver specifies the <i>MiniportSynchronousOidRequest</i> entry point when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a> function, using the <b>SynchronousOidRequestHandler</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_driver_characteristics">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a> structure.


Miniport drivers must not return NDIS_STATUS_PENDING or NDIS_STATUS_REQUEST_ABORTED from MiniportSynchronousOidRequest. Synchronous OID requests cannot be pended or cancelled.

Miniport drivers may return NDIS_STATUS_NOT_ACCEPTED after NDIS calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_device_pnp_event_notify">
       MiniportDevicePnPEventNotify</a> to notify the driver of the device’s surprise removal. However, miniport drivers may still complete the OID request with a different status code, if it is possible to do so. For more info, see each OID’s specific documentation.

Miniport drivers are expected to complete Synchronous OID requests quickly without blocking, waiting, or sleeping. Synchronous OID requests are only used for low-latency operations, and miniport drivers should strive to complete them within several milliseconds. Most OID requests are delivered to <a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-oid-requests-in-a-miniport-adapter">MiniportOidRequest</a>, which is permitted to pend or wait for longer durations.


NDIS does not serialize Synchronous OID requests against each other, against other OID requests, against <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pause">MiniportPause</a>, against <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>, or against power transitions. It is the responsibility of the miniport driver to implement its own synchronization and to fail requests that are delivered at a time when the request cannot be handled successfully.

NDIS does serialize Synchronous OID requests against <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>; NDIS guarantees that no Synchronous OID requests will be active once <i>MiniportHaltEx</i> is invoked.

Miniport drivers that implement NDIS Selective Suspend are incompatible with Synchronous OIDs and must not register a <i>MiniportSynchronousOidRequest</i> handler.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_device_pnp_event_notify">
       MiniportDevicePnPEventNotify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/handling-oid-requests-in-a-miniport-adapter">MiniportOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_miniport_driver_characteristics">NDIS_MINIPORT_DRIVER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
 

 

