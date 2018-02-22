---
UID: NC:ndis.MINIPORT_CANCEL_OID_REQUEST
title: MINIPORT_CANCEL_OID_REQUEST
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportCancelOidRequest function to cancel an OID request.
old-location: netvista\miniportcanceloidrequest.htm
old-project: netvista
ms.assetid: 42faa43d-0993-40f7-bec3-fd7c3860d5ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.miniportcanceloidrequest, MiniportCancelOidRequest callback function [Network Drivers Starting with Windows Vista], MiniportCancelOidRequest, MINIPORT_CANCEL_OID_REQUEST, MINIPORT_CANCEL_OID_REQUEST, ndis/MiniportCancelOidRequest, ndis_request_ref_8a44b849-35fd-4c19-97eb-09bd68fb97bb.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportCancelOidRequest
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_CANCEL_OID_REQUEST callback


## -description


NDIS calls a miniport driver's 
   <i>MiniportCancelOidRequest</i> function to cancel an OID request.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CANCEL_OID_REQUEST</b> type. For
   more information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_CANCEL_OID_REQUEST MiniportCancelOidRequest;

VOID MiniportCancelOidRequest(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ PVOID       RequestId
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



A driver specifies the 
    <i>MiniportCancelOidRequest</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function.

When NDIS calls 
    <i>MiniportCancelOidRequest</i>, the miniport driver should attempt to call 
    <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a> function
    as soon as possible.

The request parameters are defined in the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure at 
    <i>OidRequest</i> .

NDIS calls 
    <i>MiniportCancelOidRequest</i> either when the originator of the request cancels the request or when the
    time-out, specified at the 
    <b>Timeout</b> member, expires.

If the request processing is still not complete in a miniport driver, the driver calls the 
    <b>NdisMOidRequestComplete</b> function with the status set to NDIS_STATUS_REQUEST_ABORTED.

If the request processing is still not complete in an intermediate driver and the request was
    propagated to an underlying driver, the intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndiscanceloidrequest.md">NdisCancelOidRequest</a> function with
    the 
    <i>OidRequest</i> parameter set to the value that it sent to the underlying driver.

NDIS calls
    <i>MiniportCancelOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCancelOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCancelOidRequest</i> function that is named "MyCancelOidRequest", use the <b>MINIPORT_CANCEL_OID_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CANCEL_DIRECT_OID_REQUEST MyCancelOidRequest;</pre>
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
 MyCancelRequest(
    NDIS_HANDLE  MiniportAdapterContext,
    PVOID  RequestId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CANCEL_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nf-ndis-ndiscanceloidrequest.md">NdisCancelOidRequest</a>



<a href="..\ndis\nf-ndis-ndiscanceloidrequest.md">NdisCancelOidRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CANCEL_OID_REQUEST callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

