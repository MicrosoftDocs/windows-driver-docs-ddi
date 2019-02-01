---
UID: NC:ndis.MINIPORT_CANCEL_DIRECT_OID_REQUEST
title: MINIPORT_CANCEL_DIRECT_OID_REQUEST (ndis.h)
description: NDIS calls a miniport driver's MiniportCancelDirectOidRequest function to cancel a direct OID request.
old-location: netvista\miniportcanceldirectoidrequest.htm
tech.root: netvista
ms.assetid: 88639bb4-89f3-4e7f-9cce-ea541224572d
ms.date: 05/02/2018
ms.keywords: MINIPORT_CANCEL_DIRECT_OID_REQUEST, MINIPORT_CANCEL_DIRECT_OID_REQUEST callback, MiniportCancelDirectOidRequest, MiniportCancelDirectOidRequest callback function [Network Drivers Starting with Windows Vista], ndis/MiniportCancelDirectOidRequest, ndis_request_direct_ref_d98875f6-2607-4d82-ac0f-615a33c0b11e.xml, netvista.miniportcanceldirectoidrequest
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
-	MiniportCancelDirectOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CANCEL_DIRECT_OID_REQUEST callback function


## -description


NDIS calls a miniport driver's 
   <i>MiniportCancelDirectOidRequest</i> function to cancel a direct OID request.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the direct OID requests that
     match this value in the 
     <b>RequestId</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure.


## -returns



None




## -remarks



<i>MiniportCancelDirectOidRequest</i> is an optional function. A miniport driver registers this function
    if it handles direct OID requests. A driver specifies the 
    <i>MiniportCancelDirectOidRequest</i> entry point when it calls the 
    <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
    NdisMRegisterMiniportDriver</a> function. A miniport driver that registers the 
    <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
    MiniportDirectOidRequest</a> function must also register 
    <i>MiniportCancelDirectOidRequest</i>.

When NDIS calls 
    <i>MiniportCancelDirectOidRequest</i>, the miniport driver should attempt to call 
    <a href="https://msdn.microsoft.com/11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724">
    NdisMDirectOidRequestComplete</a> function as soon as possible.

NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> when the originator of the request cancels the request. For direct
    OID requests, NDIS does not call 
    <i>MiniportCancelDirectOidRequest</i> if the time-out expires. (The time-out is specified at the 
    <b>Timeout</b> member of each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure.)

If the request processing is still not complete in a miniport driver, the driver calls the 
    <b>NdisMDirectOidRequestComplete</b> function with the status set to NDIS_STATUS_REQUEST_ABORTED.

If the request processing is still not complete in an intermediate driver and the request was
    propagated to an underlying driver, the intermediate driver calls the 
    <a href="https://msdn.microsoft.com/bfccd901-9ce7-4873-ba9a-0e4718fd7d19">
    NdisCancelDirectOidRequest</a> function with the 
    <i>OidRequest</i> parameter set to the value that it sent to the underlying driver.

NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCancelDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCancelDirectOidRequest</i> function that is named "MyCancelDirectOidRequest", use the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CANCEL_DIRECT_OID_REQUEST MyCancelDirectOidRequest;</pre>
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
VOID
 MyCancelDirectOidRequest(
    NDIS_HANDLE  MiniportAdapterContext,
    PVOID  RequestId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">MiniportDirectOidRequest</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561621">NdisCancelDirectOidRequest</a>



<a href="https://msdn.microsoft.com/11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724">
   NdisMDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
 

 

