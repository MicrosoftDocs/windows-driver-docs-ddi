---
UID: NC:ndis.FILTER_DIRECT_OID_REQUEST_COMPLETE
title: FILTER_DIRECT_OID_REQUEST_COMPLETE
author: windows-driver-content
description: NDIS calls the FilterDirectOidRequestComplete function to complete a filter driver direct OID request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_DIRECT_OID_REQUEST_COMPLETE type.
old-location: netvista\filterdirectoidrequestcomplete.htm
old-project: netvista
ms.assetid: a97c86e9-4fd9-4e2f-9787-4fa19c38a69b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FILTER_DIRECT_OID_REQUEST_COMPLETE, FilterDirectOidRequestComplete, FilterDirectOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/FilterDirectOidRequestComplete, ndis_request_direct_ref_7c57d5c9-2a37-4602-b94e-df700652b1a9.xml, netvista.filterdirectoidrequestcomplete
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
-	FilterDirectOidRequestComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# FILTER_DIRECT_OID_REQUEST_COMPLETE callback


## -description


NDIS calls the 
  <i>FilterDirectOidRequestComplete</i> function to complete a filter driver direct OID request that queried
  or set information in an underlying driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
FILTER_DIRECT_OID_REQUEST_COMPLETE FilterDirectOidRequestComplete;

VOID FilterDirectOidRequestComplete(
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
     <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">
     NdisFDirectOidRequest</a> function.


### -param Status [in]

The final status of the request that an underlying driver or NDIS set. This parameter determines
     what 
     <i>FilterDirectOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a>.


## -returns



None




## -remarks



<i>FilterDirectOidRequestComplete</i> is an optional function. If a filter driver does not use direct OID
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function. If a filter driver defines a 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a> function,
    it must provide the 
    <i>FilterDirectOidRequestComplete</i> function.

If the 
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a> function
    returns NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterDirectOidRequestComplete</i> function to complete the OID request.

If a filter driver forwarded a request that it received in the 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a> function,
    
    <i>FilterDirectOidRequestComplete</i> should pass the completion status up the driver stack by calling the
    
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequestcomplete.md">
    NdisFDirectOidRequestComplete</a> function. In this case, the filter driver must call 
    <a href="..\ndis\nf-ndis-ndisfreecloneoidrequest.md">NdisFreeCloneOidRequest</a>, to free
    the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure, before it calls
    
    <b>NdisFDirectOidRequestComplete</b>.

A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFDirectOidRequestComplete</b> when NDIS calls 
    <i>FilterDirectOidRequestComplete</i> for such requests.

NDIS calls 
    <i>FilterDirectOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterDirectOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDirectOidRequestComplete</i> function that is named "MyDirectOidRequestComplete", use the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FILTER_DIRECT_OID_REQUEST_COMPLETE MyDirectOidRequestComplete;</pre>
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
 MyDirectOidRequestComplete(
    NDIS_HANDLE  FilterModuleContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfreecloneoidrequest.md">NdisFreeCloneOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a>



<a href="..\ndis\nf-ndis-ndisfdirectoidrequestcomplete.md">
   NdisFDirectOidRequestComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FILTER_DIRECT_OID_REQUEST_COMPLETE callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

