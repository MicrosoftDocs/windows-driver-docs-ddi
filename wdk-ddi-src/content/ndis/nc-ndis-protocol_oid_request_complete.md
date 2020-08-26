---
UID: NC:ndis.PROTOCOL_OID_REQUEST_COMPLETE
title: PROTOCOL_OID_REQUEST_COMPLETE (ndis.h)
description: The ProtocolOidRequestComplete function completes the processing of a protocol driver-initiated OID request for which the NdisOidRequest function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_OID_REQUEST_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocoloidrequestcomplete.htm
tech.root: netvista
ms.assetid: 2706577e-ba03-4347-9672-7303752ec0fe
ms.date: 05/02/2018
keywords: ["PROTOCOL_OID_REQUEST_COMPLETE callback function"]
ms.keywords: PROTOCOL_OID_REQUEST_COMPLETE, PROTOCOL_OID_REQUEST_COMPLETE callback, ProtocolOidRequestComplete, ProtocolOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolOidRequestComplete, ndis_request_ref_0460f62c-1ffe-4c81-ade3-56b5061eccb6.xml, netvista.protocoloidrequestcomplete
f1_keywords:
 - "ndis/ProtocolOidRequestComplete"
 - "ProtocolOidRequestComplete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolOidRequestComplete
targetos: Windows
req.typenames: 
---

# PROTOCOL_OID_REQUEST_COMPLETE callback function


## -description


The 
  <i>ProtocolOidRequestComplete</i> function completes the processing of a protocol
  driver-initiated OID request for which the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_OID_REQUEST_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext 
[in]
A handle to a protocol driver-allocated context area in which the protocol driver maintains
     per-binding run-time state. The driver supplied this handle when it called the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param OidRequest 
[in]
A pointer to the protocol driver-supplied 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that was
     previously passed to the 
     <b>NdisOidRequest</b> function.


### -param Status 
[in]
The final status of the request. The underlying driver or NDIS determines this final status. This
     parameter determines what 
     <i>ProtocolOidRequestComplete</i> does with the information at 
     <i>OidRequest</i>.


## -remarks



<i>ProtocolOidRequestComplete</i> uses the input value of 
    <i>Status</i> as follows:

<ul>
<li>
If 
      <i>Status</i> is NDIS_STATUS_SUCCESS, the 
      <b>BytesRead</b> or 
      <b>BytesWritten</b> member of the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure has been set
      by NDIS or the underlying driver to specify how much protocol driver-supplied information was
      transferred from the buffer at 
      <b>InformationBuffer</b> to the NIC in a set operation or how much information
      was returned at 
      <b>InformationBuffer</b> in response to a query operation.

If the protocol driver made a query, 
      <i>ProtocolOidRequestComplete</i> can use the data returned at 
      <b>InformationBuffer</b> in any way determined by the protocol driver, depending
      on the value of the 
      <b>Oid</b> member.

For example, if the protocol driver originally initiated an 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-send-packets">
      OID_GEN_MAXIMUM_SEND_PACKETS</a> query, 
      <i>ProtocolOidRequestComplete</i> might set up state variables in the 
      <i>ProtocolBindingContext</i> area to throttle the number of outstanding sends the
      driver will set up for subsequent calls to the 
      <b>NdisSendNetBufferLIsts</b> function.

</li>
<li>
If 
      <i>Status</i> is NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT, the 
      <b>BytesNeeded</b> member specifies the OID-specific value of the 
      <b>InformationBufferLength</b> member required to carry out the requested
      operation.

In these circumstances, 
      <i>ProtocolOidRequestComplete</i> can allocate sufficient buffer space for the
      request, set up another NDIS_OID_REQUEST structure with the required 
      <b>InformationBufferLength</b> and same 
      <b>Oid</b>, and retry the call to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function.

<i>ProtocolOidRequestComplete</i> can retry requests for certain other NDIS_STATUS_
      <i>XXX</i> arguments, as well, as described in the reference for the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function.

</li>
<li>
If 
      <i>Status</i> is an NDIS_STATUS_
      <i>XXX</i> value that is an unrecoverable error, 
      <i>ProtocolOidRequestComplete</i> should release the memory allocated for the
      NDIS_OID_REQUEST structure and determine whether the driver should close the binding, or adjust its
      binding-specific state information to handle continued network I/O operations on the binding.

</li>
</ul>
For global queries and sets, the underlying connectionless miniport driver's call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismoidrequestcomplete">NdisMOidRequestComplete</a> function
    causes NDIS to call the 
    <i>ProtocolOidRequestComplete</i> function. NDIS forwards the miniport
    driver-determined 
    <i>Status</i> passed to 
    <b>NdisMOidRequestComplete</b> as the input 
    <i>Status</i> to 
    <i>ProtocolOidRequestComplete</i>.

For binding-specific queries, NDIS calls the 
    <i>ProtocolOidRequestComplete</i> function itself. Because the NDIS library maintains
    bindings for all miniport drivers, NDIS can return binding-specific information only about underlying
    drivers that report their medium-type as one for which the system provides a filter library. NDIS returns
    NDIS_STATUS_NOT_SUPPORTED for protocol driver-initiated binding-specific queries to other miniport
    drivers.

For more information about system-defined OIDs, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">NDIS OIDs</a>.

<i>ProtocolOidRequestComplete</i> can be called before the protocol driver has had
    time to inspect the status code that 
    <b>NdisOidRequest</b> returns at 
    <i>Status</i>.

NDIS calls 
    <i>ProtocolOidRequestComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolOidRequestComplete</i> function that is named "MyOidRequestComplete", use the <b>PROTOCOL_OID_REQUEST_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_OID_REQUEST_COMPLETE MyOidRequestComplete;</pre>
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
 MyOidRequestComplete(
    NDIS_HANDLE  ProtocolBindingContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismoidrequestcomplete">NdisMOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-maximum-send-packets">OID_GEN_MAXIMUM_SEND_PACKETS</a>
 

 

