---
UID: NC:ndis.PROTOCOL_CL_INCOMING_CALL
title: PROTOCOL_CL_INCOMING_CALL (ndis.h)
description: The ProtocolClIncomingCall function is used by connection-oriented clients that accept incoming calls.
old-location: netvista\protocolclincomingcall.htm
tech.root: netvista
ms.assetid: 8a5922ac-b22b-444e-9ea0-3bb56e71ef33
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_INCOMING_CALL callback function"]
ms.keywords: PROTOCOL_CL_INCOMING_CALL, PROTOCOL_CL_INCOMING_CALL callback, ProtocolClIncomingCall, ProtocolClIncomingCall callback function [Network Drivers Starting with Windows Vista], condis_client_ref_8c9188c3-7134-4fab-a9c7-67862e881054.xml, ndis/ProtocolClIncomingCall, netvista.protocolclincomingcall
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClIncomingCall (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClIncomingCall (NDIS   5.1)) in Windows XP.
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
 - PROTOCOL_CL_INCOMING_CALL
 - ndis/PROTOCOL_CL_INCOMING_CALL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolClIncomingCall
---

# PROTOCOL_CL_INCOMING_CALL callback function


## -description

The 
  <i>ProtocolClIncomingCall</i> function is used by connection-oriented clients that accept incoming calls.
  Such clients must have 
  <i>ProtocolClIncomingCall</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClIncomingCall</i> function can simply return NDIS_STATUS_NOT_SUPPORTED.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_INCOMING_CALL</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolSapContext 

[in]
Specifies the handle that the client originally supplied when it registered the SAP, which the
     call manager matched to this incoming call offer.

### -param ProtocolVcContext 

[in]
Specifies the handle to the client's per-VC context area, previously returned to NDIS by its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param CallParameters 

[in, out]
Pointer to a buffer, formatted as a 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> structure, that contains
     the call parameters for this offered call.

## -returns

<i>ProtocolClIncomingCall</i> can return one of the following status codes:

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
The client accepted the incoming call offer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The client is handling this request asynchronously, and it will call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclincomingcallcomplete">
       NdisClIncomingCallComplete</a> function when the close operation is complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The client rejected the incoming call offer for some driver-determined reason.

</td>
</tr>
</table>

## -remarks

A call to 
    <i>ProtocolClIncomingCall</i> indicates that the call manager has received a request over the network from
    a signaling peer to establish a connection with this client. That is, the request to set up such a
    connection was directed to a SAP previously registered with the call manager by this client.

Depending on the signaling protocol supported by the call manager, 
    <i>ProtocolClIncomingCall</i> can modify the traffic parameters as part of the process of negotiating
    acceptance of an incoming call offer and/or, if the call manager supports QoS, the quality of service
    specification at 
    <i>CallParameters</i> . The client should copy any information it will need subsequently from this
    buffered structure if it accepts the offered call.

Assuming the call manager finds the client's modifications, if any, acceptable, NDIS next calls the
    client's 
    <i>ProtocolClIncomingCallConnected</i> function when it becomes possible for transfers to occur on the
    active VC representing the connection to the client on the remote node that originally initiated the call
    offer. If the client returns modified call parameters that are unacceptable, the call manager can tear
    down the VC it created for this offer, thereby causing calls to the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">
    ProtocolClIncomingCloseCall</a> and then 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> functions
    instead.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClIncomingCall</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClIncomingCall</i> function that is named "MyClIncomingCall", use the <b>PROTOCOL_CL_INCOMING_CALL</b> type as shown in this code example:


```cpp
PROTOCOL_CL_INCOMING_CALL MyClIncomingCall;
```

Then, implement your function as follows:


```cpp
_Use_decl_annotations_
NDIS_STATUS
 MyClIncomingCall(
    NDIS_HANDLE  ProtocolSapContext,
    NDIS_HANDLE  ProtocolVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}
```

The <b>PROTOCOL_CL_INCOMING_CALL</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_INCOMING_CALL</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclincomingcallcomplete">NdisClIncomingCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_call_connected">ProtocolClCallConnected</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_close_call">ProtocolClIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>

