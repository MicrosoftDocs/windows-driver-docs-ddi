---
UID: NC:ndis.MINIPORT_CO_OID_REQUEST
title: MINIPORT_CO_OID_REQUEST
author: windows-driver-content
description: The MiniportCoOidRequest function handles an OID request to query or set information in CoNDIS miniport driver.Note  You must declare the function by using the MINIPORT_CO_OID_REQUEST type.
old-location: netvista\miniportcooidrequest.htm
old-project: netvista
ms.assetid: 903bcdc5-9d42-4067-a054-057edc95ccf7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportCoOidRequest
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

# MINIPORT_CO_OID_REQUEST callback



## -description
The 
  <i>MiniportCoOidRequest</i> function handles an OID request to query or set information in CoNDIS miniport
  driver.



## -prototype

````
MINIPORT_CO_OID_REQUEST MiniportCoOidRequest;

NDIS_STATUS MiniportCoOidRequest(
  _In_    NDIS_HANDLE       MiniportAdapterContext,
  _In_    NDIS_HANDLE       MiniportVcContext,
  _Inout_ PNDIS_OID_REQUEST OidRequest
)
{ ... }
````


## -parameters

### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param MiniportVcContext [in]

A handle to a miniport driver-allocated context area in which the miniport driver maintains its
     per-virtual connection (VC) state. The miniport driver supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function. If the
     request is 
     not VC-specific, this parameter is <b>NULL</b>.


### -param OidRequest [in, out]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure that this parameter points to.


## -returns
<i>MiniportCoOidRequest</i> can return one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport driver either set or obtained the data as requested.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>The miniport driver will complete the request asynchronously. After the miniport driver has
       completed all processing, it must call the 
       <a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">
       NdisMCoOidRequestComplete</a> function to inform NDIS that the request is complete.
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>The request that the 
       <i>OidRequest</i> parameter specified was invalid or not recognized.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>The request that the 
       <i>OidRequest</i> parameter specified was recognized but not supported by the miniport driver.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>The buffer that the 
       <i>OidRequest</i> parameter supplied was too small to hold the requested data.
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl>The value that was specified in the 
       <b>InformationBufferLength</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure at 
       <i>OidRequest</i> is incorrect for the specified OID_<i>XXX</i> code.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>One or more of the parameters that were specified for the request at 
       <i>OidRequest</i> iwas invalid.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>After NDIS calls the 
       <a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS calls the driver's 
       <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. If the
       driver receives any OID requests before NDIS calls 
       <i>MiniportHaltEx</i>, it should immediately complete such requests with a status value of
       NDIS_STATUS_NOT_ACCEPTED.
<dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl>The miniport driver stopped processing the request. For example, NDIS called the 
       <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> or 
       <a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">
       MiniportCancelOidRequest</a> function.

 


## -remarks
NDIS calls the 
    <i>MiniportCoOidRequest</i> function to handle an OID request to query or set information in a CoNDIS
    miniport driver.

To register 
    <i>MiniportCoOidRequest</i>, miniport drivers call the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    from the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. In 
    <i>MiniportSetOptions</i>, the miniport driver initializes an 
    <a href="..\ndis\ns-ndis-_ndis_miniport_co_characteristics.md">
    NDIS_MINIPORT_CO_CHARACTERISTICS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.

NDIS calls the 
    <i>MiniportCoOidRequest</i> function either on its own behalf or on behalf of a bound protocol driver that
    called the 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> function. Miniport
    drivers should examine the request supplied at 
    <i>OidRequest</i> and take the action requested. For more information about the OIDs that miniport drivers
    handle, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.

Note that NDIS does not validate the OID-specific contents at 
    <i>OidRequest</i> . Therefore, the driver itself must validate these contents. If the driver determines
    that the value to be set is out of bounds, it should fail the request and return
    NDIS_STATUS_INVALID_DATA.

If 
    <i>MiniportCoOidRequest</i> returns NDIS_STATUS_PENDING, NDIS can call 
    <i>MiniportCoOidRequest</i> with another request, for the miniport adapter specified at 
    <i>MiniportAdapterContext</i>, before the pending request is completed. NDIS does not serialize connection
    oriented OID requests.

To define a <i>MiniportCoOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoOidRequest</i> function that is named "MyCoOidRequest", use the <b>MINIPORT_CO_OID_REQUEST</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_CO_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">MiniportCancelOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_co_characteristics.md">
   NDIS_MINIPORT_CO_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">NdisMCoOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CO_OID_REQUEST callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

