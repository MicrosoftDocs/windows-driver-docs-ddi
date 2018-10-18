---
UID: NC:ndis.PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
title: PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX
author: windows-driver-content
description: NDIS calls a protocol driver's ProtocolCloseAdapterCompleteEx function to complete a close adapter operation for which the NdisCloseAdapterEx function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX type. For more information, see the following Examples section.
old-location: netvista\protocolcloseadaptercompleteex.htm
tech.root: netvista
ms.assetid: 62cc047a-bc91-4e1e-817e-7fd509d4d90e
ms.date: 5/2/2018
ms.keywords: PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX, PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback, ProtocolCloseAdapterCompleteEx, ProtocolCloseAdapterCompleteEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolCloseAdapterCompleteEx, netvista.protocolcloseadaptercompleteex, protocol_functions_ref_ebd02bc7-54f9-4b38-a2a5-9db0b64f1747.xml
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolCloseAdapterCompleteEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX callback function


## -description


NDIS calls a protocol driver's 
  <i>ProtocolCloseAdapterCompleteEx</i> function to complete a close adapter operation for which the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561640">NdisCloseAdapterEx</a> function returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


## -returns



None




## -remarks



<i>ProtocolCloseAdapterCompleteEx</i> is a required function.

If 
    <i>ProtocolUnbindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolCloseAdapterCompleteEx</i>, this function can simply indicate that it has been called and
    return (for example, it updates the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolCloseAdapterCompleteEx</i> function to complete the unbind operation.

After the protocol driver calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561640">NdisCloseAdapterEx</a> function, the 
    <i>NdisBindingHandle</i> handle that the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function returned is
    no longer valid. Therefore, 
    <i>ProtocolCloseAdapterCompleteEx</i> cannot call any 
    <b>Ndis<i>Xxx</i></b> functions that require this handle as a parameter.

If the 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function has not already done so,
    <i>ProtocolCloseAdapterCompleteEx</i> can release the resources that the protocol driver allocated for
    per-binding network I/O operations.

If 
    <i>ProtocolUnbindAdapterEx</i> returned NDIS_STATUS_PENDING and saved the 
    <i>UnbindContext</i> handle in the context area at 
    <i>ProtocolBindingContext</i>, 
    <i>ProtocolCloseAdapterCompleteEx</i> can call the 
    <a href="https://msdn.microsoft.com/3a1daad4-d4b7-4950-be58-73612949fba9">
    NdisCompleteUnbindAdapterEx</a> function to complete the unbinding operation. Consequently, 
    <i>ProtocolCloseAdapterCompleteEx</i> should not release the context area until after it calls 
    <b>NdisCompleteUnbindAdapterEx</b>.

NDIS calls 
    <i>ProtocolCloseAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCloseAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCloseAdapterCompleteEx</i> function that is named "MyCloseAdapterCompleteEx", use the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX MyCloseAdapterCompleteEx;</pre>
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
 MyCloseAdapterCompleteEx(
    NDIS_HANDLE  ProtocolBindingContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CLOSE_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561640">NdisCloseAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561708">NdisCompleteUnbindAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

