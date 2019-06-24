---
UID: NC:ndis.FILTER_DIRECT_OID_REQUEST_COMPLETE
title: FILTER_DIRECT_OID_REQUEST_COMPLETE (ndis.h)
description: NDIS calls the FilterDirectOidRequestComplete function to complete a filter driver direct OID request that queried or set information in an underlying driver.Note  You must declare the function by using the FILTER_DIRECT_OID_REQUEST_COMPLETE type.
old-location: netvista\filterdirectoidrequestcomplete.htm
tech.root: netvista
ms.assetid: a97c86e9-4fd9-4e2f-9787-4fa19c38a69b
ms.date: 05/02/2018
ms.keywords: FILTER_DIRECT_OID_REQUEST_COMPLETE, FILTER_DIRECT_OID_REQUEST_COMPLETE callback, FilterDirectOidRequestComplete, FilterDirectOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/FilterDirectOidRequestComplete, ndis_request_direct_ref_7c57d5c9-2a37-4602-b94e-df700652b1a9.xml, netvista.filterdirectoidrequestcomplete
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- FilterDirectOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure that the filter
     driver previously passed to the 
     <a href="https://msdn.microsoft.com/dec5415b-6903-416e-819b-007ea6f7e7b5">
     NdisFDirectOidRequest</a> function.


### -param Status [in]

The final status of the request that an underlying driver or NDIS set. This parameter determines
     what 
     <i>FilterDirectOidRequestComplete</i> does with the information at 
     <i>OidRequest</i> . For a list of the possible status values, see the return values of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a>.


## -returns



None




## -remarks



<i>FilterDirectOidRequestComplete</i> is an optional function. If a filter driver does not use direct OID
    requests, it can set the entry point for this function to <b>NULL</b> when it calls the 
    <a href="https://msdn.microsoft.com/14381de2-36d9-4ec8-9d4e-7af3e6d8ecf3">
    NdisFRegisterFilterDriver</a> function. If a filter driver defines a 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,
    it must provide the 
    <i>FilterDirectOidRequestComplete</i> function.

If the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a> function
    returns NDIS_STATUS_PENDING, NDIS must call the 
    <i>FilterDirectOidRequestComplete</i> function to complete the OID request.

If a filter driver forwarded a request that it received in the 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function,    
    <i>FilterDirectOidRequestComplete</i> should pass the completion status up the driver stack by calling the    
    <a href="https://msdn.microsoft.com/b6b4d4f4-63d5-496c-9082-f2e8d1a174ec">
    NdisFDirectOidRequestComplete</a> function. In this case, the filter driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>, to free
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure, before it calls    
    <b>NdisFDirectOidRequestComplete</b>.

A filter driver should keep track of requests that it originates and ensure that it does not call 
    <b>NdisFDirectOidRequestComplete</b> when NDIS calls 
    <i>FilterDirectOidRequestComplete</i> for such requests.

NDIS calls 
    <i>FilterDirectOidRequestComplete</i> at IRQL <= DISPATCH_LEVEL.

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

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561809">NdisFDirectOidRequest</a>



<a href="https://msdn.microsoft.com/b6b4d4f4-63d5-496c-9082-f2e8d1a174ec">
   NdisFDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561845">NdisFreeCloneOidRequest</a>
 

 

