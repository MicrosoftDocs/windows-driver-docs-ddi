---
UID: NC:ndis.MINIPORT_CO_OID_REQUEST
title: MINIPORT_CO_OID_REQUEST
author: windows-driver-content
description: The MiniportCoOidRequest function handles an OID request to query or set information in CoNDIS miniport driver.Note  You must declare the function by using the MINIPORT_CO_OID_REQUEST type.
old-location: netvista\miniportcooidrequest.htm
tech.root: netvista
ms.assetid: 903bcdc5-9d42-4067-a054-057edc95ccf7
ms.date: 5/2/2018
ms.keywords: MINIPORT_CO_OID_REQUEST, MINIPORT_CO_OID_REQUEST callback, MiniportCoOidRequest, MiniportCoOidRequest callback function [Network Drivers Starting with Windows Vista], condis_request_ref_fff124d4-8671-441b-817f-30b4275dca68.xml, ndis/MiniportCoOidRequest, netvista.miniportcooidrequest
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportCoOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CO_OID_REQUEST callback function


## -description


The 
  <i>MiniportCoOidRequest</i> function handles an OID request to query or set information in CoNDIS miniport
  driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_OID_REQUEST</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param OPTIONAL

A handle to a miniport driver-allocated context area in which the miniport driver maintains its
     per-virtual connection (VC) state. The miniport driver supplied this handle to NDIS from its 
     <a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a> function. If the
     request is 
     not VC-specific, this parameter is <b>NULL</b>.

### -param NdisRequest

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure that this parameter points to.


## -returns



<i>MiniportCoOidRequest</i> can return one of the following status values:

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
The miniport driver either set or obtained the data as requested.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver will complete the request asynchronously. After the miniport driver has
       completed all processing, it must call the 
       <a href="https://msdn.microsoft.com/18242351-3dec-40df-b112-2335253903d2">
       NdisMCoOidRequestComplete</a> function to inform NDIS that the request is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The request that the 
       <i>OidRequest</i> parameter specified was invalid or not recognized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The request that the 
       <i>OidRequest</i> parameter specified was recognized but not supported by the miniport driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the 
       <i>OidRequest</i> parameter supplied was too small to hold the requested data.

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
       <b>InformationBufferLength</b> member of the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure at 
       <i>OidRequest</i> is incorrect for the specified OID_<i>XXX</i> code.

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
       <i>OidRequest</i> iwas invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
After NDIS calls the 
       <a href="https://msdn.microsoft.com/e41240c0-17be-42ef-a72c-c5311115cf64">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS calls the driver's 
       <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function. If the
       driver receives any OID requests before NDIS calls 
       <i>MiniportHaltEx</i>, it should immediately complete such requests with a status value of
       NDIS_STATUS_NOT_ACCEPTED.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver stopped processing the request. For example, NDIS called the 
       <a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a> or 
       <a href="https://msdn.microsoft.com/42faa43d-0993-40f7-bec3-fd7c3860d5ad">
       MiniportCancelOidRequest</a> function.

</td>
</tr>
</table>
 




## -remarks



NDIS calls the 
    <i>MiniportCoOidRequest</i> function to handle an OID request to query or set information in a CoNDIS
    miniport driver.

To register 
    <i>MiniportCoOidRequest</i>, miniport drivers call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a> function. In 
    <i>MiniportSetOptions</i>, the miniport driver initializes an 
    <a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
    NDIS_MINIPORT_CO_CHARACTERISTICS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.

NDIS calls the 
    <i>MiniportCoOidRequest</i> function either on its own behalf or on behalf of a bound protocol driver that
    called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a> function. Miniport
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

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoOidRequest</i> function that is named "MyCoOidRequest", use the <b>MINIPORT_CO_OID_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CO_OID_REQUEST MyCoOidRequest;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NDIS_STATUS
 MyCoOidRequest(
    NDIS_HANDLE  MiniportAdapterContext,
    NDIS_HANDLE  MiniportVcContext,
    PNDIS_OID_REQUEST  OidRequest
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CO_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/42faa43d-0993-40f7-bec3-fd7c3860d5ad">MiniportCancelOidRequest</a>



<a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a>



<a href="https://msdn.microsoft.com/e41240c0-17be-42ef-a72c-c5311115cf64">
   MiniportDevicePnPEventNotify</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="https://msdn.microsoft.com/9348c338-9fb4-4eee-a50f-f709748da56b">
   NDIS_MINIPORT_CO_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563568">NdisMCoOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

