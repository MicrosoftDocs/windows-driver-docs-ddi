---
UID: NC:ndis.MINIPORT_DIRECT_OID_REQUEST
title: MINIPORT_DIRECT_OID_REQUEST (ndis.h)
description: NDIS calls a miniport driver's MiniportDirectOidRequest function to handle a direct OID request to query or set information in the driver.
old-location: netvista\miniportdirectoidrequest.htm
tech.root: netvista
ms.assetid: 60daba60-3e04-4e98-a458-4dc263f17761
ms.date: 05/02/2018
ms.keywords: MINIPORT_DIRECT_OID_REQUEST, MINIPORT_DIRECT_OID_REQUEST callback, MiniportDirectOidRequest, MiniportDirectOidRequest callback function [Network Drivers Starting with Windows Vista], ndis/MiniportDirectOidRequest, ndis_request_direct_ref_8650027d-37db-4165-9bf6-c239b6db2919.xml, netvista.miniportdirectoidrequest
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
-	MiniportDirectOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_DIRECT_OID_REQUEST callback function


## -description


NDIS calls a miniport driver's 
   <i>MiniportDirectOidRequest</i> function to handle a direct OID request to query or set information in the
   driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_DIRECT_OID_REQUEST</b> type. For
   more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param OidRequest [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure that is provided.


## -returns



<i>MiniportDirectOidRequest</i> can return one of the following status values:

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
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver will complete the request asynchronously. After the miniport driver has
       completed all processing, it must call the 
       <a href="https://msdn.microsoft.com/11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724">
       NdisMDirectOidRequestComplete</a> function to inform NDIS that the request is complete.

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
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
After calling the 
       <a href="https://msdn.microsoft.com/e41240c0-17be-42ef-a72c-c5311115cf64">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS called the driver's 
       <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function. If the
       driver received any OID requests before NDIS calls 
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
       <a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a> function.

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
       determine if this status is allowed, see the OID reference page.. For more information about
       NDIS_STATUS_INDICATION_REQUIRED, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> and 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>.

</td>
</tr>
</table>
 




## -remarks



<i>MiniportDirectOidRequest</i> is an optional function. A miniport driver registers this function if it
    handles direct OID requests. A driver specifies the 
    <i>MiniportDirectOidRequest</i> entry point when it calls the 
    <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
    NdisMRegisterMiniportDriver</a> function. A miniport driver that registers the 
    <a href="https://msdn.microsoft.com/88639bb4-89f3-4e7f-9cce-ea541224572d">
    MiniportCancelDirectOidRequest</a> function must also register 
    <i>MiniportDirectOidRequest</i>.

NDIS calls the 
    <i>MiniportDirectOidRequest</i> function either on its own behalf or on behalf of a bound protocol driver
    that called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561746">NdisDirectOidRequest</a> function.
    Miniport drivers should examine the request that is supplied at the 
    <i>OidRequest</i> parameter and take the action requested.

Note that NDIS does not validate the OID-specific contents at 
    <i>OidRequest</i>. Therefore, the driver itself must validate these contents. If the driver determines
    that the value to be set is out of bounds, it should fail the request and return
    NDIS_STATUS_INVALID_DATA.

NDIS does not serialize requests that it sends to 
    <i>MiniportDirectOidRequest</i> with other OID requests. The miniport driver must be able to handle
    multiple calls to 
    <i>MiniportDirectOidRequest</i> when other requests that are sent to 
    <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a> or 
    <i>MiniportDirectOidRequest</i> are outstanding.

<div class="alert"><b>Note</b>  The NDIS check-for-hang logic will not reset a miniport driver that is not
    responding if the miniport driver is waiting in the context of the 
    <i>MiniportOidRequest</i> call. Therefore, miniport drivers should not wait for hardware operations to
    complete from within the context of the 
    <i>MiniportOidRequest</i> call. Instead, the driver can return NDIS_STATUS_PENDING and queue a work
    item.</div>
<div> </div>
NDIS calls 
    <i>MiniportDirectOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDirectOidRequest</i> function that is named "MyDirectOidRequest", use the <b>MINIPORT_DIRECT_OID_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_DIRECT_OID_REQUEST MyDirectOidRequest;</pre>
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
 MyDirectOidRequest(
    NDIS_HANDLE  MiniportAdapterContext,
    PNDIS_OID_REQUEST  OidRequest
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/88639bb4-89f3-4e7f-9cce-ea541224572d">
   MiniportCancelDirectOidRequest</a>



<a href="https://msdn.microsoft.com/e41240c0-17be-42ef-a72c-c5311115cf64">
   MiniportDevicePnPEventNotify</a>



<a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">MiniportDirectOidRequest</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a>



<a href="https://msdn.microsoft.com/15f82163-a1b5-4cef-a53e-8a97adb2cd92">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561746">NdisDirectOidRequest</a>



<a href="https://msdn.microsoft.com/11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724">
   NdisMDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
 

 

