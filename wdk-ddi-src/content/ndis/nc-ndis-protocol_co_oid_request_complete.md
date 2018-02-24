---
UID: NC:ndis.PROTOCOL_CO_OID_REQUEST_COMPLETE
title: PROTOCOL_CO_OID_REQUEST_COMPLETE
author: windows-driver-content
description: The ProtocolCoOidRequestComplete function completes the processing of an asynchronous CoNDIS OID request.Note  You must declare the function by using the PROTOCOL_CO_OID_REQUEST_COMPLETE type.
old-location: netvista\protocolcooidrequestcomplete.htm
old-project: netvista
ms.assetid: 16883c64-3cc6-4f50-8be7-7c58c422a717
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.protocolcooidrequestcomplete, ProtocolCoOidRequestComplete callback function [Network Drivers Starting with Windows Vista], ProtocolCoOidRequestComplete, PROTOCOL_CO_OID_REQUEST_COMPLETE, PROTOCOL_CO_OID_REQUEST_COMPLETE, ndis/ProtocolCoOidRequestComplete, condis_request_ref_14f11d94-41dd-44b1-9117-20c8d22278aa.xml
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	ProtocolCoOidRequestComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CO_OID_REQUEST_COMPLETE callback


## -description


The 
  <i>ProtocolCoOidRequestComplete</i> function completes the processing of an asynchronous
  CoNDIS OID request.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_OID_REQUEST_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CO_OID_REQUEST_COMPLETE ProtocolCoOidRequestComplete;

VOID ProtocolCoOidRequestComplete(
  _In_    NDIS_HANDLE       ProtocolAfContext,
  _In_    NDIS_HANDLE       ProtocolVcContext,
  _In_    NDIS_HANDLE       ProtocolPartyContext,
  _Inout_ PNDIS_OID_REQUEST OidRequest,
  _In_    NDIS_STATUS       Status
)
{ ... }
````


## -parameters




### -param ProtocolAfContext [in]

A handle that identifies an address family (AF) context area. If the driver is a client, it
     supplied this handle when it called the 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">
     NdisClOpenAddressFamilyEx</a> function to connect itself to the call manager. If the driver is a call
     manager or miniport call manager (MCM), it supplied this handle from its 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


### -param ProtocolVcContext [in]

A handle that identifies the active virtual connection (VC) that the driver requested or set
     information for, if the request was VC-specific. Otherwise, this parameter is <b>NULL</b>.


### -param ProtocolPartyContext [in]

A handle that identifies the party on a multipoint VC that the driver requested or set information
     for, if the request is party-specific. Otherwise, this parameter is <b>NULL</b>.


### -param OidRequest [in, out]

A pointer to the driver-supplied 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that was
     previously passed to the 
     <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> or 
     <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function.


### -param Status [in]

The final status of the request. The target driver or NDIS determines this final status. This
     parameter determines what 
     <i>ProtocolCoOidRequestComplete</i> does with the information at 
     <i>OidRequest</i>.


## -returns



None




## -remarks



NDIS calls the 
    <i>ProtocolCoOidRequestComplete</i> function to complete the processing of CoNDIS
    client, call manager, or MCM OID request for which the 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> function or 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function returned
    NDIS_STATUS_PENDING.

To register 
    <i>ProtocolCoOidRequestComplete</i> as a client, a driver initializes an 
    <a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
    NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function.
    To register 
    <i>ProtocolCoOidRequestComplete</i> as a call manager, a driver initializes an 
    <a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
    NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter of 
    <b>NdisSetOptionalHandlers</b>.

The target driver is the driver that serviced the OID information request. A target driver's call to
    the 
    <a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">NdisMCoOidRequestComplete</a>, 
    <a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">NdisCoOidRequestComplete</a>, or 
    <a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">
    NdisMCmOidRequestComplete</a> function caused NDIS to call the 
    <i>ProtocolCoOidRequestComplete</i> function. NDIS forwards the value of the 
    <i>Status</i> parameter that was passed to these functions as the input 
    <i>Status</i> parameter to 
    <i>ProtocolCoOidRequestComplete</i>.

<i>ProtocolCoOidRequestComplete</i> uses the input value of 
    <i>Status</i> as follows:

<ul>
<li>
If 
      <i>Status</i> is NDIS_STATUS_SUCCESS, the 
      <b>BytesRead</b> or 
      <b>BytesWritten</b> member of the 
      <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that the 
      <i>OidRequest</i> parameter points to specifies how much information was transferred
      from the buffer in the 
      <b>InformationBuffer</b> member of NDIS_OID_REQUEST to the target driver or how much information was
      returned at 
      <b>InformationBuffer</b>, respectively.

If the driver made a query request, 
      <i>ProtocolCoOidRequestComplete</i> can use the data that is returned in 
      <b>InformationBuffer</b> as appropriate for the value that is specified in the 
      <b>Oid</b> member of NDIS_OID_REQUEST.

</li>
<li>
If 
      <i>Status</i> is NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT, the 
      <b>BytesNeeded</b> member of the NDIS_OID_REQUEST structure that 
      <i>OidRequest</i> points to specifies the OID-specific value of the 
      <b>InformationBufferLength</b> member of NDIS_OID_REQUEST that is required to carry out the requested
      operation.

In these circumstances, 
      <i>ProtocolCoOidRequestComplete</i> can allocate sufficient buffer space for the
      request, set up another 
      <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure with the
      required value for 
      <b>InformationBufferLength</b>, and retry the OID request.

</li>
<li>
If 
      <i>Status</i> is an NDIS_STATUS_
      <i>XXX</i> value that is an unrecoverable error, 
      <i>ProtocolCoOidRequestComplete</i> should release the memory for the
      NDIS_OID_REQUEST structure. 
      <i>ProtocolCoOidRequestComplete</i> should also determine whether the driver should
      close the binding or adjust its binding-specific state information to handle continued network I/O
      operations on the binding.

</li>
</ul>
For more information about system-defined OIDs, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.

<i>ProtocolCoOidRequestComplete</i> can be called before the driver has had time to
    inspect the status code that 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> or 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> returns.

NDIS calls 
    <i>ProtocolCoOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoOidRequestComplete</i> function that is named "MyCoOidRequestComplete", use the <b>PROTOCOL_CO_OID_REQUEST_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_OID_REQUEST_COMPLETE MyCoOidRequestComplete;</pre>
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
 MyCoOidRequestComplete(
    NDIS_HANDLE  ProtocolAfContext,
    NDIS_HANDLE  ProtocolVcContext,
    NDIS_HANDLE  ProtocolPartyContext,
    PNDIS_OID_REQUEST  OidRequest,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="..\ndis\nf-ndis-ndismcooidrequestcomplete.md">NdisMCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">NdisCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>



<a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>



<a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">NdisCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">NdisMCmOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">NdisMCmOidRequestComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CO_OID_REQUEST_COMPLETE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

