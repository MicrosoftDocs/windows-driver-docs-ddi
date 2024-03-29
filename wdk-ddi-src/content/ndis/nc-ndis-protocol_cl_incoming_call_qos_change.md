---
UID: NC:ndis.PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
title: PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE (ndis.h)
description: The ProtocolClIncomingCallQoSChange function is used by connection-oriented clients on networks that support dynamic quality-of-service.
old-location: netvista\protocolclincomingcallqoschange.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE callback function"]
ms.keywords: PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE, PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE callback, ProtocolClIncomingCallQoSChange, ProtocolClIncomingCallQoSChange callback function [Network Drivers Starting with Windows Vista], condis_client_ref_09f3fdc8-cdc0-4b49-82c2-bd5816c9d5a9.xml, ndis/ProtocolClIncomingCallQoSChange, netvista.protocolclincomingcallqoschange
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClIncomingCallQoSChange (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClIncomingCallQoSChange (NDIS 5.1)) in Windows XP.
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
 - PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
 - ndis/PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
---

# PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE callback function


## -description

The 
  <i>ProtocolClIncomingCallQoSChange</i> function is used by connection-oriented clients on networks that
  support dynamic quality-of-service. Such clients must have 
  <i>ProtocolClIncomingCallQoSChange</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClIncomingCallQoSChange</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolVcContext [in]


Specifies the handle to the client's per-VC context area for the VC on which a request to modify
     the quality of service has come in over the network.

### -param CallParameters [in]


Pointer to a buffer, formatted as a 
     <a href="/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> structure, that contains
     the new QoS specification.

## -remarks

A call to 
    <i>ProtocolClIncomingCallQoSChange</i> indicates to the client that a remote peer has requested a change
    in the quality of service on this call. The new quality of service is described at 
    <i>CallParameters</i> . The client can accept the requested change by simply returning control. Otherwise,    
    <i>ProtocolClIncomingCallQoSChange</i> should tear down the call with 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClIncomingCallQoSChange</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClIncomingCallQoSChange</i> function that is named "MyClIncomingCallQoSChange", use the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> type as shown in this code example:


```
PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE MyClIncomingCallQoSChange;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyClIncomingCallQoSChange(
    NDIS_HANDLE  ProtocolVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}
```

The <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmodifycallqos">NdisClModifyCallQoS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_modify_qos_call">ProtocolCmModifyCallQoS</a>

