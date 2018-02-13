---
UID: NC:ndis.FILTER_OID_REQUEST_COMPLETE
title: FILTER_OID_REQUEST_COMPLETE
author: windows-driver-content
description: NDIS calls the FilterOidRequestComplete function to complete a filter driver request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_OID_REQUEST_COMPLETE type.
old-location: netvista\filteroidrequestcomplete.htm
old-project: netvista
ms.assetid: 2dba21d8-512b-4a1a-9cf9-0240c94a69a0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.filteroidrequestcomplete, FilterOidRequestComplete callback function [Network Drivers Starting with Windows Vista], FilterOidRequestComplete, FILTER_OID_REQUEST_COMPLETE, FILTER_OID_REQUEST_COMPLETE, ndis/FilterOidRequestComplete, ndis_request_ref_c1c43e8e-536a-4d7a-9341-c39c33778db3.xml
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
-	FilterOidRequestComplete
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# FILTER_OID_REQUEST_COMPLETE callback


## -description


NDIS calls the 
  <i>FilterOidRequestComplete</i> function to complete a filter driver request that queried or set information
  in an underlying driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
FILTER_OID_REQUEST_COMPLETE FilterOidRequestComplete;

VOID FilterOidRequestComplete(
  _In_ NDIS_HANDLE       FilterModuleContext,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
)
{ ... }
````


## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that the filter
     driver previously passed to the 
     <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a> function.


### -param Status [in]

The final status of the request set by an underlying driver or by NDIS. This parameter determines
     what 
     <i>FilterOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>.


## -returns



None




## -remarks



<i>FilterOidRequestComplete</i> is an optional function. If a filter driver does not use OID requests, it
    can set the entry point for this function to <b>NULL</b> when it calls the 
    <b>NdisFRegisterFilterDriver</b> function. If a filter driver defines a 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function, it must
    provide the 
    <i>FilterOidRequestComplete</i> function.

If the 
    <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a> function returns
    NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterOidRequestComplete</i> function to complete the OID request.

If a filter driver forwarded a request that it received in the 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function, 
    <i>FilterOidRequestComplete</i> should pass the completion status up the driver stack by calling the 
    <a href="..\ndis\nf-ndis-ndisfoidrequestcomplete.md">NdisFOidRequestComplete</a> function.
    The filter driver must call 
    <a href="..\ndis\nf-ndis-ndisfreecloneoidrequest.md">NdisFreeCloneOidRequest</a>, to free
    the NDIS_OID_REQUEST structure, before it calls 
    <b>NdisFOidRequestComplete</b>.

A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFOidRequestComplete</b> when NDIS calls 
    <i>FilterOidRequestComplete</i> for such requests.

NDIS calls 
    <i>FilterOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterOidRequestComplete</i> function that is named "MyOidRequestComplete", use the <b>FILTER_OID_REQUEST_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_OID_REQUEST_COMPLETE MyOidRequestComplete;</pre>
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
 MyOidRequestComplete(
    NDIS_HANDLE  FilterModuleContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfreecloneoidrequest.md">NdisFreeCloneOidRequest</a>



<a href="..\ndis\nf-ndis-ndisfoidrequestcomplete.md">NdisFOidRequestComplete</a>



<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_OID_REQUEST_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

