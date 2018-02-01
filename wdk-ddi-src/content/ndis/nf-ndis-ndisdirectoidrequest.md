---
UID: NF:ndis.NdisDirectOidRequest
title: NdisDirectOidRequest function
author: windows-driver-content
description: The NdisDirectOidRequest function forwards a direct OID request to the underlying drivers to query the capabilities or status of an adapter or set the state of an adapter.
old-location: netvista\ndisdirectoidrequest.htm
old-project: netvista
ms.assetid: 771e5761-beea-4a31-9ebe-d65e9157f1f4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_request_direct_ref_3a98c424-2d24-4841-87a7-e782d4e6c79d.xml, ndis/NdisDirectOidRequest, NdisDirectOidRequest, netvista.ndisdirectoidrequest, NdisDirectOidRequest function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	NdisDirectOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisDirectOidRequest function


## -description


The 
  <b>NdisDirectOidRequest</b> function forwards a direct OID request to the underlying drivers to query the
  capabilities or status of an adapter or set the state of an adapter.


## -syntax


````
NDIS_STATUS NdisDirectOidRequest(
  _In_ NDIS_HANDLE       NdisBindingHandle,
  _In_ PNDIS_OID_REQUEST OidRequest
);
````


## -parameters




### -param NdisBindingHandle [in]

The handle that the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function returns that
     identifies the target miniport adapter on the binding.


### -param OidRequest [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation that is requested with a given OID_<i>Xxx</i> code to either query the status of an adapter or to set the state of an adapter.


## -returns


The underlying driver determines which NDIS_STATUS_<i>XXX</i> code 
     <b>NdisDirectOidRequest</b> returns, but it is usually one of the following values:
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
The request operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The request is being handled asynchronously, and NDIS will call the caller's 
       <a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
       ProtocolDirectOidRequestComplete</a> function when the request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The OID_<i>Xxx</i> code that was specified in the 
       <b>Oid</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>-structured buffer at 
       <i>OidRequest</i> was invalid or unsupported by the underlying driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST-structured buffer at 
       <i>OidRequest</i> did not match the requirements for the given OID_<i>Xxx</i> code. If the information buffer was too small, the 
       <b>BytesNeeded</b> member contains the correct value for 
       <b>InformationBufferLength</b> on return from 
       <b>NdisDirectOidRequest</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The data that was supplied at 
       <b>InformationBuffer</b> in the given NDIS_OID_REQUEST structure was invalid for the given OID_<i>Xxx</i> code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED or NDIS_STATUS_NOT_RECOGNIZED</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver does not support the requested operation. For 
       <b>NdisDirectOidRequest</b>, NDIS can also return this status if the calling driver has not registered
       a 
       <a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
       ProtocolDirectOidRequestComplete</a> function.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request could not be satisfied because of a resource shortage. Typically, this return value
       indicates that an attempt to allocate memory was unsuccessful, but it does not necessarily indicate
       that the same request, submitted later, will be failed for the same reason.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver attempted the requested operation, typically a set on a NIC, but it
       failed. For example, an attempt to set too many multicast addresses might cause the return of this
       value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_CLOSING or NDIS_STATUS_CLOSING_INDICATING</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver failed the requested operation because a close operation is in
       progress.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESET_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
The underlying miniport driver cannot satisfy the request at this time because it is currently
       resetting the affected NIC. The caller's 
       <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function was or
       will be called with NDIS_STATUS_RESET_START to indicate that a reset is in progress. This return value
       does not necessarily indicate that the same request, submitted later, will be failed for the same
       reason.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This value typically is a non-specific default, returned when none of the more specific
       NDIS_STATUS_<i>Xxx</i> values caused the underlying driver to fail the request.

</td>
</tr>
</table> 



## -remarks


The 
    <b>NdisDirectOidRequest</b> function cannot be used for general OID requests. For general OID requests,
    use the 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function instead. 
    <b>NdisDirectOidRequest</b> can be used only for OIDs that NDIS supports for use with the direct OID
    interface. For example, the following OIDs can be used:


<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a>


A protocol driver must allocate sufficient memory to hold the information buffer that is associated
    with the specified OID. The driver must also allocate and set up the buffer at the 
    <i>OidRequest</i> parameter before it calls 
    <b>NdisDirectOidRequest</b>. Both buffers must be allocated from nonpaged pool because the underlying
    driver runs at raised IRQL while processing the request.

<b>NdisDirectOidRequest</b> forwards a request to underlying drivers or handles the request itself. If the
    next-lower driver is an NDIS intermediate driver, the intermediate driver can call 
    <b>NdisDirectOidRequest</b> with an OID-specific request of its own before completing the request that the
    higher-level driver originally submitted.

A driver that calls 
    <b>NdisDirectOidRequest</b> must register the 
    <a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
    ProtocolDirectOidRequestComplete</a> function.

The direct OID request interface is similar to the general OID request interface. For more information
    about issuing general requests, see 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>.
<div class="alert"><b>Note</b>  Although Direct OID requests are not generally serialized, NDIS itself may still pend a request with NDIS_STATUS_PENDING and queue the request for later completion. For example, NDIS may pend and queue a Direct OID request sent to a selective suspend miniport that is currently in a low power state. Protocols and filters must be prepared to handle an NDIS_STATUS_PENDING code, even if the underlying miniport would complete the request synchronously.</div><div> </div>


## -see-also

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>

<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-update-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</a>

<a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">
   ProtocolDirectOidRequestComplete</a>

<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDirectOidRequest function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

