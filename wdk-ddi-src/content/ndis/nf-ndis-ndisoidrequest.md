---
UID: NF:ndis.NdisOidRequest
title: NdisOidRequest function
author: windows-driver-content
description: The NdisOidRequest function forwards a request to the underlying drivers to query the capabilities or status of an adapter or set the state of an adapter.
old-location: netvista\ndisoidrequest.htm
old-project: netvista
ms.assetid: a3ddeec4-0414-48ed-ab3b-5df252682655
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisOidRequest, NdisOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisOidRequest, ndis_request_ref_d60ed5b8-bcb7-4195-8767-618ab55f090b.xml, netvista.ndisoidrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_OID_Function
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
-	NdisOidRequest
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisOidRequest function


## -description


The 
  <b>NdisOidRequest</b> function forwards a request to the underlying drivers to query the capabilities or
  status of an adapter or set the state of an adapter.


## -parameters




### -param NdisBindingHandle [in]

The handle returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function that
     identifies the target adapter on the binding.


### -param OidRequest [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested with a given OID_<i>XXX</i> code to either query the status of an adapter or to set the state of an adapter.


## -returns



The underlying driver determines which NDIS_STATUS_<i>XXX</i> code 
     <b>NdisOidRequest</b> returns, but it is usually one of the following values:

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
       <a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">
       ProtocolOidRequestComplete</a> function when the request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The OID_<i>XXX</i> code specified in the 
       <b>Oid</b> member of the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>-structured buffer at 
       <i>OidRequest</i> is invalid or unsupported by the underlying driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The value specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST-structured buffer at 
       <i>OidRequest</i> does not match the requirements for the given OID_<i>XXX</i> code. If the information buffer is too small, the 
       <b>BytesNeeded</b> member contains the correct value for 
       <b>InformationBufferLength</b> on return from 
       <b>NdisOidRequest</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The data supplied at 
       <b>InformationBuffer</b> in the given NDIS_OID_REQUEST structure is invalid for the given OID_<i>XXX</i> code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED or NDIS_STATUS_NOT_RECOGNIZED</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver does not support the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request could not be satisfied due to a resource shortage. Usually, this return value
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
The underlying driver attempted the requested operation, usually a set on a NIC, but it failed.
       For example, an attempt to set too many multicast addresses might cause the return of this
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
       <a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a> function was or
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
This value usually is a nonspecific default, returned when none of the more specific
       NDIS_STATUS_<i>XXX</i> caused the underlying driver to fail the request.

</td>
</tr>
</table>
 




## -remarks



A protocol driver must allocate sufficient memory to hold the information buffer that is associated
    with the specified OID. The driver must also allocate and set up the buffer at 
    <i>OidRequest</i> before it calls 
    <b>NdisOidRequest</b>. Both buffers must be allocated from nonpaged pool because the underlying driver
    runs at raised IRQL while processing the request.

<b>NdisOidRequest</b> forwards a request to underlying drivers or handles the request itself.. If the
    next-lower driver is an NDIS intermediate driver, it can call 
    <b>NdisOidRequest</b> with an OID-specific request of its own before completing the request originally
    submitted by the higher-level driver.

Some errors returned are recoverable, including the following:

That is, a driver can modify the packet at 
    <i>OidRequest</i> appropriately to correct the OID_<i>XXX</i> code or the size or contents of the buffer at 
    <b>InformationBuffer</b> and resubmit the request packet to 
    <b>NdisOidRequest</b>. The same packet might be satisfied on resubmission to 
    <b>NdisOidRequest</b> if the original call indicated a reset in progress or that a resource shortage,
    which might be temporary, prevented that request from being carried out.

The NDIS library maintains bindings for underlying miniport drivers. NDIS can return information for
    binding-specific queries if a given OID is associated with a system-defined medium type for which the
    system provides a filter library.

For more information about the general and media-specific OIDs and their respective associated
    information buffers, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>



<a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOidRequest function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

