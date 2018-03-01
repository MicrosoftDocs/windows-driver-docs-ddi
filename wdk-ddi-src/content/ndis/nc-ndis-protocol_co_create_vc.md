---
UID: NC:ndis.PROTOCOL_CO_CREATE_VC
title: PROTOCOL_CO_CREATE_VC
author: windows-driver-content
description: The ProtocolCoCreateVc function is a required function that allocates resources necessary for a call manager or client to activate and maintain a virtual connection (VC).Note  You must declare the function by using the PROTOCOL_CO_CREATE_VC type.
old-location: netvista\protocolcocreatevc.htm
old-project: netvista
ms.assetid: b086dd24-74f5-474a-8684-09bf92ac731b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PROTOCOL_CO_CREATE_VC, ProtocolCoCreateVc, ProtocolCoCreateVc callback function [Network Drivers Starting with Windows Vista], condis_protocol_ref_f0a7e657-70d5-4cd1-a42a-684cefe1dc60.xml, ndis/ProtocolCoCreateVc, netvista.protocolcocreatevc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCoCreateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCoCreateVc (NDIS   5.1)) in Windows XP.
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
-	ProtocolCoCreateVc
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CO_CREATE_VC callback


## -description


The 
  <i>ProtocolCoCreateVc</i> function is a required function that allocates resources necessary for a call
  manager or client to activate and maintain a virtual connection (VC).
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_CREATE_VC</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CO_CREATE_VC ProtocolCoCreateVc;

NDIS_STATUS ProtocolCoCreateVc(
  _In_  NDIS_HANDLE  ProtocolAfContext,
  _In_  NDIS_HANDLE  NdisVcHandle,
  _Out_ PNDIS_HANDLE ProtocolVcContext
)
{ ... }
````


## -parameters




### -param ProtocolAfContext [in]

Specifies the handle to a protocol-allocated context area in which the call manager or client
     maintains its per-open state. The call manager supplied this handle from its 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function. The client
     supplied this handle when it called 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a> from
     its 
     <i>ProtocolCoAfRegisterNotify</i> function.


### -param NdisVcHandle [in]

Specifies a handle, supplied by NDIS, that uniquely identifies this virtual connection. This
     handle is opaque to the protocol driver and reserved for NDIS library use. However, the call manager and
     client must save this handle to pass in subsequent calls to 
     <b>NdisCo/Cl/Cm/MCm<i>Xxx</i></b> functions that concern this VC.


### -param ProtocolVcContext [out]

Specifies the handle to a protocol-supplied context area in which the call manager or client
     maintains state about this virtual connection.


## -returns



<i>ProtocolCoCreateVc</i> returns the status of its operation(s) as one of the following values:

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
Indicates that the call manager or client successfully allocated and/or initialized any
       necessary resources that were needed to establish and maintain a virtual connection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager or client was unable to allocate and/or initialize its resources
       for establishing and maintaining a virtual connection.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager or client could not set itself into a state where it could
        establish a virtual connection. This can could be an error return value propagated from another NDIS
        library routine.

<div class="alert"><b>Note</b>  Call managers or clients cannot return NDIS_STATUS_PENDING from their 
        <i>ProtocolCoCreateVc</i> functions. Returning pending will render this virtual
        connection unusable and the NDIS library will call the client or call manager to delete it.</div>
<div> </div>
</td>
</tr>
</table>
 




## -remarks



The 
    <i>ProtocolCoCreateVc</i> function of a call manager or client is called whenever the corresponding client
    or call manager, respectively, calls 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>. Clients initiate the
    creation of VCs in the process of setting up their outgoing calls before they call 
    <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>. A call manager initiates
    the creation of a VC in the process of notifying its client that the CM received an incoming call offer
    from a remote node that is directed to a SAP already registered with the CM by that client before the CM
    calls 
    <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
    NdisCmDispatchIncomingCall</a>.

<i>ProtocolCoCreateVc</i> performs any necessary allocations of dynamic resources and structures that the
    call manager or client requires to perform subsequent operations on a VC that will be activated. Such
    resources include, but are not limited to, memory buffers, data structures, events, and other such
    similar resources. Call managers and clients should also initialize any relevant per-VC structures that
    they will need when a call is established.

Connection-oriented protocol drivers must store the handle for the VC, specified in 
    <i>NdisVcHandle</i>, in their per-VC state area to be used in future operations on this virtual
    connection. The 
    <i>NdisVcHandle</i> is as required parameter to the 
    <b>NdisCo<i>Xxx</i></b>, 
    <b>NdisCm<i>Xxx</i></b>, and/or 
    <b>NdisCl<i>Xxx</i></b> that such a connection-oriented protocol subsequently calls.

When a call manager or client has allocated memory for its own per-VC data and initialized its state,
    the address of this data structure should be set in the handle before returning control to NDIS. To do
    this, dereference the handle and store a pointer to the protocol-allocated data area as the value of the
    handle. For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>*ProtocolVcContext = SomeBuffer;</pre>
</td>
</tr>
</table></span></div>
If 
    <i>ProtocolCoCreateVc</i> cannot allocate the resource it needs to carry out subsequent network I/O
    operations, it should free all resources that were allocated for this VC and return control with a status
    of NDIS_STATUS_RESOURCES.

If 
    <i>ProtocolCoCreateVc</i> has completed its required operations and has made the call manager or client
    ready to carry out call initialization for this virtual connection, 
    <i>ProtocolCoCreateVc</i> should return control as quickly as possible with a status of
    NDIS_STATUS_SUCCESS.

Calls to 
    <i>ProtocolCoCreateVc</i> are inherently synchronous in nature. That is, 
    <i>ProtocolCoCreateVc</i><u>cannot</u> return NDIS_STATUS_PENDING.

After a call manager's 
    <i>ProtocolCoCreateVc</i> function returns control, the call manager's 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function will be
    called to establish a connection to a remote node. Call managers should not take any action in 
    <i>ProtocolCmMakeCall</i> that actually establishes a call because it is possible the VC will be destroyed
    before a call is established due to an error condition in another component of connection-oriented
    NDIS.

After a client's 
    <i>ProtocolCoCreateVc</i> function returns control, the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a> function
    will be notified when a remote-initiated request to connect on a SAP previously registered by the client
    comes in over the network.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoCreateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoCreateVc</i> function that is named "MyCoCreateVc", use the <b>PROTOCOL_CO_CREATE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_CREATE_VC MyCoCreateVc;</pre>
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
 MyCoCreateVc(
    NDIS_HANDLE  ProtocolAfContext,
    NDIS_HANDLE  NdisVcHandle,
    PNDIS_HANDLE  ProtocolVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_CREATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_CREATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>



<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CO_CREATE_VC callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

