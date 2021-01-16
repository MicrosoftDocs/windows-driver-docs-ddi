---
UID: NC:ndis.PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
title: PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX (ndis.h)
description: NDIS calls a protocol driver's ProtocolCloseAdapterCompleteEx function to complete a close adapter operation for which the NdisCloseAdapterEx function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX type. For more information, see the following Examples section.
old-location: netvista\protocolcloseadaptercompleteex.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback function"]
ms.keywords: PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX, PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback, ProtocolCloseAdapterCompleteEx, ProtocolCloseAdapterCompleteEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolCloseAdapterCompleteEx, netvista.protocolcloseadaptercompleteex, protocol_functions_ref_ebd02bc7-54f9-4b38-a2a5-9db0b64f1747.xml
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
 - ndis/PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
---

# PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback function


## -description

NDIS calls a protocol driver's 
  <i>ProtocolCloseAdapterCompleteEx</i> function to complete a close adapter operation for which the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

## -remarks

<i>ProtocolCloseAdapterCompleteEx</i> is a required function.

If 
    <i>ProtocolUnbindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolCloseAdapterCompleteEx</i>, this function can simply indicate that it has been called and
    return (for example, it updates the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolCloseAdapterCompleteEx</i> function to complete the unbind operation.

After the protocol driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a> function, the 
    <i>NdisBindingHandle</i> handle that the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function returned is
    no longer valid. Therefore, 
    <i>ProtocolCloseAdapterCompleteEx</i> cannot call any 
    <b>Ndis<i>Xxx</i></b> functions that require this handle as a parameter.

If the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">
    ProtocolUnbindAdapterEx</a> function has not already done so,
    <i>ProtocolCloseAdapterCompleteEx</i> can release the resources that the protocol driver allocated for
    per-binding network I/O operations.

If 
    <i>ProtocolUnbindAdapterEx</i> returned NDIS_STATUS_PENDING and saved the 
    <i>UnbindContext</i> handle in the context area at 
    <i>ProtocolBindingContext</i>, 
    <i>ProtocolCloseAdapterCompleteEx</i> can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompleteunbindadapterex">
    NdisCompleteUnbindAdapterEx</a> function to complete the unbinding operation. Consequently, 
    <i>ProtocolCloseAdapterCompleteEx</i> should not release the context area until after it calls 
    <b>NdisCompleteUnbindAdapterEx</b>.

NDIS calls 
    <i>ProtocolCloseAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCloseAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCloseAdapterCompleteEx</i> function that is named "MyCloseAdapterCompleteEx", use the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> type as shown in this code example:


```
PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX MyCloseAdapterCompleteEx;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCloseAdapterCompleteEx(
    NDIS_HANDLE  ProtocolBindingContext
    )
  {...}
```

The <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscloseadapterex">NdisCloseAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompleteunbindadapterex">NdisCompleteUnbindAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_unbind_adapter_ex">ProtocolUnbindAdapterEx</a>

