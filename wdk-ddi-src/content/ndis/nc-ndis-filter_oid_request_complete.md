---
UID: NC:ndis.FILTER_OID_REQUEST_COMPLETE
title: FILTER_OID_REQUEST_COMPLETE (ndis.h)
description: NDIS calls the FilterOidRequestComplete function to complete a filter driver request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_OID_REQUEST_COMPLETE type.
old-location: netvista\filteroidrequestcomplete.htm
tech.root: netvista
ms.assetid: 2dba21d8-512b-4a1a-9cf9-0240c94a69a0
ms.date: 05/02/2018
ms.keywords: FILTER_OID_REQUEST_COMPLETE, FILTER_OID_REQUEST_COMPLETE callback, FilterOidRequestComplete, FilterOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/FilterOidRequestComplete, ndis_request_ref_c1c43e8e-536a-4d7a-9341-c39c33778db3.xml, netvista.filteroidrequestcomplete
ms.topic: callback
f1_keywords:
 - "ndis/FilterOidRequestComplete"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- FilterOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_OID_REQUEST_COMPLETE callback function


## -description


NDIS calls the 
  <i>FilterOidRequestComplete</i> function to complete a filter driver request that queried or set information
  in an underlying driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param FilterModuleContext [in]

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that the filter
     driver previously passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a> function.


### -param Status [in]

The final status of the request set by an underlying driver or by NDIS. This parameter determines
     what 
     <i>FilterOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>.


## -returns



None




## -remarks



<i>FilterOidRequestComplete</i> is an optional function. If a filter driver does not use OID requests, it
    can set the entry point for this function to <b>NULL</b> when it calls the 
    <b>NdisFRegisterFilterDriver</b> function. If a filter driver defines a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a> function, it must
    provide the 
    <i>FilterOidRequestComplete</i> function.

If the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a> function returns
    NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterOidRequestComplete</i> function to complete the OID request.

If a filter driver forwarded a request that it received in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a> function, 
    <i>FilterOidRequestComplete</i> should pass the completion status up the driver stack by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequestcomplete">NdisFOidRequestComplete</a> function.
    The filter driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreecloneoidrequest">NdisFreeCloneOidRequest</a>, to free
    the NDIS_OID_REQUEST structure, before it calls 
    <b>NdisFOidRequestComplete</b>.

A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFOidRequestComplete</b> when NDIS calls 
    <i>FilterOidRequestComplete</i> for such requests.

NDIS calls 
    <i>FilterOidRequestComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
The <b>FILTER_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfoidrequestcomplete">NdisFOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreecloneoidrequest">NdisFreeCloneOidRequest</a>
 

 

