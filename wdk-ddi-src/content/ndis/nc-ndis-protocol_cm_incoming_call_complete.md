---
UID: NC:ndis.PROTOCOL_CM_INCOMING_CALL_COMPLETE
title: PROTOCOL_CM_INCOMING_CALL_COMPLETE (ndis.h)
description: The ProtocolCmIncomingCallComplete function is required.
old-location: netvista\protocolcmincomingcallcomplete.htm
tech.root: netvista
ms.assetid: 353e929b-17c8-47e8-82fd-b646e93a5b9a
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_INCOMING_CALL_COMPLETE callback function"]
ms.keywords: PROTOCOL_CM_INCOMING_CALL_COMPLETE, PROTOCOL_CM_INCOMING_CALL_COMPLETE callback, ProtocolCmIncomingCallComplete, ProtocolCmIncomingCallComplete callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_0760b8c9-29b8-40ff-b8a9-03e4c4f792e2.xml, ndis/ProtocolCmIncomingCallComplete, netvista.protocolcmincomingcallcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolCmIncomingCallComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolCmIncomingCallComplete (NDIS 5.1)) in Windows XP.
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
 - PROTOCOL_CM_INCOMING_CALL_COMPLETE
 - ndis/PROTOCOL_CM_INCOMING_CALL_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - ProtocolCmIncomingCallComplete
---

# PROTOCOL_CM_INCOMING_CALL_COMPLETE callback function


## -description

The 
  <i>ProtocolCmIncomingCallComplete</i> function is required. When NDIS calls this function, 
  <i>ProtocolCmIncomingCallComplete</i> indicates to the call manager that the connection-oriented client has
  finished processing of an incoming call offer that the call manager previously dispatched through 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">
  NdisCmDispatchIncomingCall</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param Status 

[in]
Indicates the final status of the operation to dispatch an incoming call to a connection-oriented
     client.

### -param CallMgrVcContext 

[in]
Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param CallParameters 

[in]
Pointer to the call parameters as specified by the call manager in the call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>.
     The signaling protocol determines which call parameters, if any, the call manager can change.

## -remarks

When the connection-oriented client has completed processing of an incoming connection offer that the
    call manager dispatched to it, this routine will be called if 
    <b>NdisCmDispatchIncomingCall</b> returned NDIS_STATUS_PENDING. The final status of the incoming call is
    found in 
    <i>Status</i>. Possible values for 
    <i>Status</i> include, but are not limited to:



If the client accepts the incoming call, the call manager should send signaling message(s) to indicate
    to the calling entity that the call has been accepted. If the client does not accept the call, the call
    manager should send signaling message(s) to indicate that the call has been rejected.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmIncomingCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmIncomingCallComplete</i> function that is named "MyCmIncomingCallComplete", use the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> type as shown in this code example:


```
PROTOCOL_CM_INCOMING_CALL_COMPLETE MyCmIncomingCallComplete;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCmIncomingCallComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}
```

The <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_reg_sap">ProtocolCmRegisterSap</a>