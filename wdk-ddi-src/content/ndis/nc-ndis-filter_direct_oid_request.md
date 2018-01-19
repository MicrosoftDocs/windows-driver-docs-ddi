---
UID: NC:ndis.FILTER_DIRECT_OID_REQUEST
title: FILTER_DIRECT_OID_REQUEST
author: windows-driver-content
description: NDIS calls a filter driver's FilterDirectOidRequest function to process a direct OID request that is associated with the specified filter module.Note  You must declare the function by using the FILTER_DIRECT_OID_REQUEST type.
old-location: netvista\filterdirectoidrequest.htm
old-project: netvista
ms.assetid: a39f4b50-0183-4f92-82f2-3c8e2e2d0632
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FilterDirectOidRequest
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_DIRECT_OID_REQUEST callback



## -description
NDIS calls a filter driver's 
  <i>FilterDirectOidRequest</i> function to process a direct OID request that is
  associated with the specified filter module.



## -prototype

````
FILTER_DIRECT_OID_REQUEST FilterDirectOidRequest;

NDIS_STATUS FilterDirectOidRequest(
  _In_ NDIS_HANDLE       FilterModuleContext,
  _In_ PNDIS_OID_REQUEST OidRequest
)
{ ... }
````


## -parameters

### -param FilterModuleContext [in]

A handle to the context area for the filter module that is the target of this request. The filter
     driver created and initialized this context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested, including the OID_
     <i>Xx</i> code. The structure can specify either a query request or a set
     request


## -returns
<i>FilterDirectOidRequest</i> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>FilterDirectOidRequest</i> successfully completed the filter driver's query or
       set operation for this filter module.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The filter driver will complete the request asynchronously. After the driver completes the
       request, it must call the 
       <a href="..\ndis\nf-ndis-ndisfdirectoidrequestcomplete.md">
       NdisFDirectOidRequestComplete</a> function to inform NDIS that the request is complete.
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>The request that 
       <i>OidRequest</i> specified was invalid or not recognized.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><i>FilterDirectOidRequest</i> does not support the OID; the OID is optional.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>The buffer that 
       <i>OidRequest</i> supplied was too small to hold the requested data.
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl>For a query operation, the 
       <b>InformationBufferLength</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure does not
       match the length that the given OID requires. 
       <i>FilterDirectOidRequest</i> returned the required buffer size, in bytes, in the 
       <b>BytesNeeded</b> member of the NDIS_OID_REQUEST structure.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>For a set operation, the data that was supplied in the 
       <b>InformationBuffer</b> member of the NDIS_OID_REQUEST structure was invalid for the given OID.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl><i>FilterDirectOidRequest</i> attempted to gather the requested information but was
       unsuccessful.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>FilterDirectOidRequest</i> failed because of insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><i>N</i> one of the preceding return values applies. The filter driver should call
       the 
       <a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a> function
       with parameters that specify the reason for the failure.

 


## -remarks
<i>FilterDirectOidRequest</i> is an optional function. If a filter driver does not use
    direct OID requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <b>NdisFRegisterFilterDriver</b> function. If a filter driver defines a 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request_complete.md">
    FilterDirectOidRequestComplete</a> function, it must provide the 
    <i>FilterDirectOidRequest</i> function.

NDIS calls the filter driver's 
    <i>FilterDirectOidRequest</i> function to process direct OID requests that are
    originated by overlying drivers. Filter drivers can forward such requests to underlying drivers by
    calling the 
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a> function. As
    an option, a filter driver can also complete a request immediately without forwarding the request.

Before the driver calls 
    <b>NdisFDirectOidRequest</b>, the driver must allocate an 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure and transfer the
    request information to the new structure by calling the 
    <a href="..\ndis\nf-ndis-ndisallocatecloneoidrequest.md">
    NdisAllocateCloneOidRequest</a> function.

To complete a request synchronously, the filter driver returns NDIS_STATUS_SUCCESS or a failure
    status. If the driver returns NDIS_STATUS_PENDING, it must call the 
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequestcomplete.md">
    NdisFDirectOidRequestComplete</a> function to inform NDIS that the request is complete.

For a query operation, 
    <i>FilterDirectOidRequest</i> returns the requested information in the 
    <b>InformationBuffer</b> member and sets the variable in the 
    <b>BytesWritten</b> member of the NDIS_OID_REQUEST structure to the amount of information it returned. The
    underlying drivers do this if the filter driver passed the request on with 
    <b>NdisFDirectOidRequest</b>.

For a set operation
    <i>, FilterDirectOidRequest</i> can use the data in the 
    <b>InformationBuffer</b> member of the NDIS_OID_REQUEST structure to set the information that the given
    OID requires. In this case, 
    <i>FilterDirectOidRequest</i> sets the variable at 
    <b>BytesRead</b> to the amount of the supplied data that it used. The underlying drivers set 
    <b>BytesRead</b> in this way if the filter driver passed the request on with 
    <b>NdisFDirectOidRequest</b>.

NDIS does not serialize requests that it sends to 
    <i>FilterDirectOidRequest</i> with other OID requests. The filter driver must be able
    to handle multiple calls to 
    <i>FilterDirectOidRequest</i> when other requests that are sent to 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> or 
    <i>FilterDirectOidRequest</i> are outstanding.

NDIS calls 
    <i>FilterDirectOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

To define a <i>FilterDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDirectOidRequest</i> function that is named "MyDirectOidRequest", use the <b>FILTER_DIRECT_OID_REQUEST</b> type as shown in this code example:

Then, implement your function as follows:

The <b>FILTER_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_direct_oid_request_complete.md">
   FilterDirectOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatecloneoidrequest.md">NdisAllocateCloneOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfdirectoidrequestcomplete.md">
   NdisFDirectOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_DIRECT_OID_REQUEST callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

