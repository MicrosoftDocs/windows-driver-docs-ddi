---
UID: NC:ndis.FILTER_DIRECT_OID_REQUEST_COMPLETE
title: FILTER_DIRECT_OID_REQUEST_COMPLETE (ndis.h)
description: NDIS calls the FilterDirectOidRequestComplete function to complete a filter driver direct OID request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_DIRECT_OID_REQUEST_COMPLETE type.
old-location: netvista\filterdirectoidrequestcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FILTER_DIRECT_OID_REQUEST_COMPLETE callback function"]
ms.keywords: FILTER_DIRECT_OID_REQUEST_COMPLETE, FILTER_DIRECT_OID_REQUEST_COMPLETE callback, FilterDirectOidRequestComplete, FilterDirectOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/FilterDirectOidRequestComplete, ndis_request_direct_ref_7c57d5c9-2a37-4602-b94e-df700652b1a9.xml, netvista.filterdirectoidrequestcomplete
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FILTER_DIRECT_OID_REQUEST_COMPLETE
 - ndis/FILTER_DIRECT_OID_REQUEST_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - FILTER_DIRECT_OID_REQUEST_COMPLETE
---

# FILTER_DIRECT_OID_REQUEST_COMPLETE callback function


## -description

NDIS calls the 
  <i>FilterDirectOidRequestComplete</i> function to complete a filter driver direct OID request that queried
  or set information in an underlying driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param FilterModuleContext [in]


A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param OidRequest [in]


A pointer to the 
     <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure that the filter
     driver previously passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">
     NdisFDirectOidRequest</a> function.

### -param Status [in]


The final status of the request that an underlying driver or NDIS set. This parameter determines
     what 
     <i>FilterDirectOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a>.

## -remarks

<i>FilterDirectOidRequestComplete</i> is an optional function. If a filter driver does not use direct OID
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function. If a filter driver defines a 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a> function,
    it must provide the 
    <i>FilterDirectOidRequestComplete</i> function.

If the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a> function
    returns NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterDirectOidRequestComplete</i> function to complete the OID request.

If a filter driver forwarded a request that it received in the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a> function,    
    <i>FilterDirectOidRequestComplete</i> should pass the completion status up the driver stack by calling the    
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequestcomplete">
    NdisFDirectOidRequestComplete</a> function. In this case, the filter driver must call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreecloneoidrequest">NdisFreeCloneOidRequest</a>, to free
    the 
    <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure, before it calls    
    <b>NdisFDirectOidRequestComplete</b>.

A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFDirectOidRequestComplete</b> when NDIS calls 
    <i>FilterDirectOidRequestComplete</i> for such requests.

NDIS calls 
    <i>FilterDirectOidRequestComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>FilterDirectOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>FilterDirectOidRequestComplete</i> function that is named "MyDirectOidRequestComplete", use the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> type as shown in this code example:


```
FILTER_DIRECT_OID_REQUEST_COMPLETE MyDirectOidRequestComplete;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyDirectOidRequestComplete(
    NDIS_HANDLE  FilterModuleContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS Status
    )
  {...}
```

The <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>FILTER_DIRECT_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request">FilterDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequestcomplete">
   NdisFDirectOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreecloneoidrequest">NdisFreeCloneOidRequest</a>

