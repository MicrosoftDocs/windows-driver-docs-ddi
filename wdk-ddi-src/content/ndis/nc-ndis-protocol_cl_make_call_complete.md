---
UID: NC:ndis.PROTOCOL_CL_MAKE_CALL_COMPLETE
title: PROTOCOL_CL_MAKE_CALL_COMPLETE (ndis.h)
description: The ProtocolClMakeCallComplete function is used by connection-oriented NDIS clients that make outgoing calls.
old-location: netvista\protocolclmakecallcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_MAKE_CALL_COMPLETE callback function"]
ms.keywords: PROTOCOL_CL_MAKE_CALL_COMPLETE, PROTOCOL_CL_MAKE_CALL_COMPLETE callback, ProtocolClMakeCallComplete, ProtocolClMakeCallComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_1c839b17-947a-44cb-85d1-d6246b82a827.xml, ndis/ProtocolClMakeCallComplete, netvista.protocolclmakecallcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClMakeCallComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClMakeCallComplete   (NDIS 5.1)) in Windows XP.
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
 - PROTOCOL_CL_MAKE_CALL_COMPLETE
 - ndis/PROTOCOL_CL_MAKE_CALL_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolClMakeCallComplete
---

# PROTOCOL_CL_MAKE_CALL_COMPLETE callback function


## -description

The 
  <i>ProtocolClMakeCallComplete</i> function is used by connection-oriented NDIS clients that make outgoing
  calls. Such clients must have 
  <i>ProtocolClMakeCallComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClMakeCallComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param Status 

[in]
Specifies the final status of the client's original call to 
     <b>NdisClMakeCall</b>, which can be one of the following:
     





#### NDIS_STATUS_SUCCESS

The client's attempt to set up a virtual connection succeded. Consequently, the client can
       proceed to make transfers on the active VC using the 
       <i>NdisVcHandle</i> returned by 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>, which the client has
       stored in its per-VC context area at 
       <i>ProtocolVcContext</i> .



#### NDIS_STATUS_RESOURCES

NDIS, the call manager, or an underlying driver could not allocate sufficient resources to set
       up the connection.



#### NDIS_STATUS_XXX

The call manager or underlying miniport driver failed to establish an active connection and NDIS
       propagated this driver-determined failure status to the client.

### -param ProtocolVcContext 

[in]
Specifies the handle to the client's per-VC context area, which the client originally supplied to
     NDIS when it called 
     <b>NdisCoCreateVc</b> to set up the VC for its outgoing call.

### -param NdisPartyHandle 

[in, optional]
If 
     <i>Status</i> is NDIS_STATUS_SUCCESS and the client created a multipoint VC by passing an explicit 
     <i>ProtocolPartyContext</i> handle to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>, this is a valid 
     <i>NdisPartyHandle</i> . Otherwise, this parameter is <b>NULL</b>.
     

<i>ProtocolClMakeCallComplete</i> must save any valid input 
     <i>NdisPartyHandle</i>, usually in the client's per-party context area. The client must use this handle
     if (or when) it makes a subsequent call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a> that refers to this
     party.

### -param CallParameters 

[in]
Pointer to a buffered CO_CALL_PARAMETERS structure. The client allocated this buffer and
     initialized this structure with client-determined data before passing this pointer to 
     <b>NdisClMakeCall</b>. While processing the client's request, the call manager can modify this data to
     reflect the results of its negotiation with the network or with a signaling peer.

## -remarks

A call to 
    <i>ProtocolClMakeCallComplete</i> indicates that the call manager has completed processing the client's
    request to establish a virtual connection with 
    <b>NdisClMakeCall</b>.

If the client's attempt to establish an outgoing call is unsuccessful (input 
    <i>Status</i> is anything except NDIS_STATUS_SUCCESS), 
    <i>ProtocolClMakeCallComplete</i> should do the following:

<ul>
<li>
Release or prepare for reuse the 
      <i>ProtocolPartyContext</i> area, if any, and the buffer at 
      <i>CallParameters</i> that the client allocated.

</li>
<li>
Tear down the client-created VC with a call to 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a> and release or prepare for
      reuse the client-allocated 
      <i>ProtocolVcContext</i> area.

</li>
</ul>
Otherwise, 
    <i>ProtocolClMakeCallComplete</i> should do the following:

<ol>
<li>
Check the 
      <b>Flags</b> member of the structure at 
      <i>CallParameters</i> to see whether CALL_PARAMETERS_CHANGED is set, which indicates that the call
      manager modified the client-supplied call parameters.

</li>
<li>
If so, examine the data at 
      <i>CallParameters</i> to determine whether they are acceptable for this connection.

For example, the client might retain the buffered call parameters for the active VC, save the 
      <i>NdisPartyHandle</i> if this is a multipoint VC, and generally make the client ready for subsequent
      transfers and other operations on the active VC if it finds the given call parameters satisfactory.

</li>
<li>
If not, the signaling protocol determines whether the client can attempt to renegotiate for
      acceptable call parameters with the call manager.

For example, a particular call manager might allow its clients to call 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a> one or more
      times in these circumstances.

</li>
<li>
If the CM-modified call parameters are unacceptable and further renegotiation is impossible, 
      <i>ProtocolClMakeCallComplete</i> must tear down the call with 
      <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

In this case, 
      <i>ProtocolClMakeCallComplete</i> should 
      <u>not</u> attempt to release any client-allocated resources on return from 
      <b>NdisClCloseCall</b> but can simply return control. Instead, the client should release the resources
      it allocated (or prepare them for reuse) within its 
      <i>ProtocolClCloseCallComplete</i> function.

</li>
</ol>
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClMakeCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClMakeCallComplete</i> function that is named "MyClMakeCallComplete", use the <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> type as shown in this code example:


```
PROTOCOL_CL_MAKE_CALL_COMPLETE MyClMakeCallComplete;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyClMakeCallComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolVcContext,
    NDIS_HANDLE  NdisPartyHandle,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}
```

The <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscldropparty">NdisClDropParty</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmmakecallcomplete">NdisCmMakeCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmmakecallcomplete">NdisMCmMakeCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_close_call_complete">ProtocolClCloseCallComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a>
