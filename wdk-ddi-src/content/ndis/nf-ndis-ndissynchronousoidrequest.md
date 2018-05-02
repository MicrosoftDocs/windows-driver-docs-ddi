---
UID: NF:ndis.NdisSynchronousOidRequest
title: NdisSynchronousOidRequest function
author: windows-driver-content
description: Protocol drivers call the NdisSynchronousOidRequest function to originate a new Synchronous OID request and issue it to underlying drivers.
old-location: netvista\ndissynchronousoidrequest.htm
old-project: netvista
ms.assetid: BF539DDA-59ED-4010-88BC-3C7D8DC475EF
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisSynchronousOidRequest, NdisSynchronousOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisSynchronousOidRequest, netvista.ndissynchronousoidrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
-	NdisSynchronousOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSynchronousOidRequest function


## -description


Protocol drivers call the <b>NdisSynchronousOidRequest</b> function to originate a new Synchronous OID request and issue it to underlying drivers.


## -parameters




### -param NdisBindingHandle [in]

The handle returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function that identifies the target miniport adapter on the binding.


### -param OidRequest [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that specifies
     the operation that is requested with a given OID_<i>Xxx</i> code. The structure can specify an OID query, set, or method request.


## -returns



The underlying driver determines which NDIS_STATUS_<i>XXX</i> code 
     <b>NdisSynchronousOidRequest</b> returns, but it is usually one of the following values:

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
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The OID_<i>Xxx</i> code that was specified in the 
       <b>Oid</b> member of the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>-structured buffer at 
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
       <b>NdisSynchronousOidRequest</b>.

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
This value typically is a non-specific default, returned when none of the more specific
       NDIS_STATUS_<i>Xxx</i> values caused the underlying driver to fail the request.

</td>
</tr>
</table>
 




## -remarks



The <b>NdisSynchronousOidRequest</b> function cannot be used for general OID requests. For general OID requests, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a> function instead. <b>NdisSynchronousOidRequest</b> can be used only for OIDs that NDIS supports for use with the Synchronous OID interface. Most protocol drivers do not need to call <b>NdisSynchronousOidRequest</b>

Protocol drivers must not close the adapter binding until any Synchronous OID requests originated by the protocol driver are completed.


Protocol drivers are not required to implement <a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a> or <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">ProtocolDirectOidRequestComplete</a> in order to call <b>NdisSynchronousOidRequest</b>. As its name suggests, a Synchronous OID request always completes synchronously, so there is no asynchronous callback.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">ProtocolDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>



<a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a>
 

 

