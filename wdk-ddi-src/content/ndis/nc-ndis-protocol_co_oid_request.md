---
UID: NC:ndis.PROTOCOL_CO_OID_REQUEST
title: PROTOCOL_CO_OID_REQUEST
author: windows-driver-content
description: The ProtocolCoOidRequest function handles OID requests that CoNDIS clients or stand-alone call managers initiate by calls to the NdisCoOidRequest function or that a miniport call manager (MCM) driver initiates by calls to the NdisMCmOidRequest function.Note  You must declare the function by using the PROTOCOL_CO_OID_REQUEST type. For more information, see the following Examples section.
old-location: netvista\protocolcooidrequest.htm
old-project: netvista
ms.assetid: 8247396f-8781-45da-aba1-a31a2a26a46f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PROTOCOL_CO_OID_REQUEST, ProtocolCoOidRequest, ProtocolCoOidRequest callback function [Network Drivers Starting with Windows Vista], condis_request_ref_b02b012f-58cc-4dd6-be48-6e1cc4f00b24.xml, ndis/ProtocolCoOidRequest, netvista.protocolcooidrequest
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
-	ProtocolCoOidRequest
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CO_OID_REQUEST callback


## -description


The 
  <i>ProtocolCoOidRequest</i> function handles OID requests that CoNDIS clients or stand-alone call managers
  initiate by calls to the 
  <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> function or that a
  miniport call manager (MCM) driver initiates by calls to the 
  <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_OID_REQUEST</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CO_OID_REQUEST ProtocolCoOidRequest;

NDIS_STATUS ProtocolCoOidRequest(
  _In_    NDIS_HANDLE       ProtocolAfContext,
  _In_    NDIS_HANDLE       ProtocolVcContext,
  _In_    NDIS_HANDLE       ProtocolPartyContext,
  _Inout_ PNDIS_OID_REQUEST OidRequest
)
{ ... }
````


## -parameters




### -param ProtocolAfContext [in]

A handle that identifies an address family (AF) context area. If the driver is a client, it
     supplied this handle when it called the 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">
     NdisClOpenAddressFamilyEx</a> function to connect itself to the call manager. If the driver is a call
     manager, it supplied this handle from its 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


### -param ProtocolVcContext [in]

A handle that identifies the virtual connection (VC) to query or set information on, if the
     request is VC-specific. Otherwise, this parameter is <b>NULL</b>.


### -param ProtocolPartyContext [in]

A handle that identifies the party on a multipoint VC to query or set information on, if the
     request is party-specific. Otherwise, this parameter is <b>NULL</b>.


### -param OidRequest [in, out]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the target driver to handle. Depending on the request, the
     driver returns requested information in the structure that 
     <i>OidRequest</i> points to.


## -returns



<i>ProtocolCoOidRequest</i> can return one of the following:

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
The client or call manager carried out the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The client, or call manager is handling this request asynchronously, and it will call the 
       <a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">
       NdisCoOidRequestComplete</a> function or the 
       <a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">
       NdisMCmOidRequestComplete</a> function when the requested operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The driver is failing the request because the caller of the 
       <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> or 
       <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function did not
       supply an adequate value for the 
       <b>InformationBuffer</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure for the given
       request. The driver set the 
       <b>BytesNeeded</b> member of NDIS_OID_REQUEST in the buffer at the 
       <i>OidRequest</i> parameter to the OID-specific value of the 
       <b>InformationBufferLength</b> member that is required to carry out the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The client or call manager failed the request for some driver-determined reason, such as invalid
       input data that was specified for a set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The client or call manager failed this request because it did not recognize the OID_GEN_CO_<i>XXX</i> code in the 
       <b>Oid</b> member in the buffer at 
       <i>NdisRequest</i>.

</td>
</tr>
</table>
 




## -remarks



The 
    <i>ProtocolCoOidRequest</i> function is required for CoNDIS clients, call managers, and MCMs. 
    <i>ProtocolCoOidRequest</i> is similar to the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a> function.

CoNDIS clients and call managers send information to each other by specifying a non-<b>NULL</b> value in the 
    <i>NdisAfHandle</i> parameter when they call the 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a> function. Similarly,
    MCMs call the 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> with explicit values
    for 
    <i>NdisAfHandle</i> to communicate information to clients. Such calls to 
    <b>NdisCoOidRequest</b> or 
    <b>NdisMCmOidRequest</b> cause NDIS to call the 
    <i>ProtocolCoOidRequest</i> function of the targeted client, call manager, or MCM that is associated with
    the specified AF handle.

To register 
    <i>ProtocolCoOidRequest</i> as a client, a driver initializes an 
    <a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
    NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function.
    To register 
    <i>ProtocolCoOidRequest</i> as a call manager, a driver initializes an 
    <a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
    NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a> structure and passes it at the 
    <i>OptionalHandlers</i> parameter.

If the 
    <i>NdisVcHandle</i> and 
    <i>NdisPartyHandle</i> parameters of 
    <b>NdisCoOidRequest</b> or 
    <b>NdisMCmOidRequest</b> are <b>NULL</b>, the request is global in nature. That is, an explicit value for 
    <i>NdisVcHandle</i> or 
    <i>NdisPartyHandle</i> indicates that 
    <i>ProtocolCoOidRequest</i> should satisfy the given request on a per-VC or per-party basis,
    respectively.

The buffer at the 
    <i>OidRequest</i> parameter was allocated from nonpaged pool and is, therefore, accessible at raised IRQL.
    The caller of 
    <a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>(or 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>) must release this
    buffer and the internal buffer at the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that 
    <i>OidRequest</i> points to.

If 
    <i>ProtocolCoOidRequest</i> returns NDIS_STATUS_PENDING, the driver must subsequently call the 
    <a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">
    NdisCoOidRequestComplete</a> function, or the 
    <a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">
    NdisMCmOidRequestComplete</a> function for an MCM driver, when the driver completes the request.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoOidRequest</i> function that is named "MyCoOidRequest", use the <b>PROTOCOL_CO_OID_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_OID_REQUEST MyCoOidRequest;</pre>
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
 MyCoOidRequest(
    NDIS_HANDLE  ProtocolAfContext,
    NDIS_HANDLE  ProtocolVcContext,
    NDIS_HANDLE  ProtocolPartyContext,
    PNDIS_OID_REQUEST  OidRequest
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-miniport_co_oid_request.md">MiniportCoOidRequest</a>



<a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\ns-ndis-_ndis_co_call_manager_optional_handlers.md">
   NDIS_CO_CALL_MANAGER_OPTIONAL_HANDLERS</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndiscooidrequestcomplete.md">NdisCoOidRequestComplete</a>



<a href="..\ndis\nf-ndis-ndiscooidrequest.md">NdisCoOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\ns-ndis-_ndis_co_client_optional_handlers.md">
   NDIS_CO_CLIENT_OPTIONAL_HANDLERS</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequestcomplete.md">NdisMCmOidRequestComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CO_OID_REQUEST callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

