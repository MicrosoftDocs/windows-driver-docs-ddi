---
UID: NC:ndis.PROTOCOL_OPEN_ADAPTER_COMPLETE_EX
title: PROTOCOL_OPEN_ADAPTER_COMPLETE_EX (ndis.h)
description: NDIS calls a protocol driver's ProtocolOpenAdapterCompleteEx function to complete an open adapter operation for which the NdisOpenAdapterEx function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_OPEN_ADAPTER_COMPLETE_EX type. For more information, see the following Examples section.
old-location: netvista\protocolopenadaptercompleteex.htm
tech.root: netvista
ms.assetid: 59d18822-8ce2-4506-90d7-9f1cdc7a9e10
ms.date: 05/02/2018
ms.keywords: PROTOCOL_OPEN_ADAPTER_COMPLETE_EX, PROTOCOL_OPEN_ADAPTER_COMPLETE_EX callback, ProtocolOpenAdapterCompleteEx, ProtocolOpenAdapterCompleteEx callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolOpenAdapterCompleteEx, netvista.protocolopenadaptercompleteex, protocol_functions_ref_d47f5a23-aa11-4fc8-9dec-a1ecb3184d9a.xml
f1_keywords:
 - "ndis/ProtocolOpenAdapterCompleteEx"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolOpenAdapterCompleteEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_OPEN_ADAPTER_COMPLETE_EX callback function


## -description


NDIS calls a protocol driver's 
  <i>ProtocolOpenAdapterCompleteEx</i> function to complete an open adapter operation for which the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The protocol driver maintains the
     per-binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called 
     <b>NdisOpenAdapterEx</b>.


### -param Status [in]

The final status of the open operation for the underlying miniport driver. This status value is
     NDIS_STATUS_SUCCESS if the binding was established or any error status that the underlying driver
     determines.


## -remarks



The 
    <i>ProtocolOpenAdapterCompleteEx</i> function is required. A protocol driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function.
    NDIS calls the driver's 
    <i>ProtocolOpenAdapterCompleteEx</i> function after a pending open operation is complete.

If 
    <i>ProtocolBindAdapterEx</i> is waiting for NDIS to call 
    <i>ProtocolOpenAdapterCompleteEx</i>, this function can simply save the status and indicate that it has
    been called (for example, it can update the 
    <i>ProtocolBindingContext</i> context area). This allows the 
    <i>ProtocolBindAdapterEx</i> function to complete the bind operation.

If the 
    <i>ProtocolBindAdapterEx</i> function has not already done so, 
    <i>ProtocolOpenAdapterCompleteEx</i> can allocate the resources that the driver requires for the
    binding.

If
    <i>ProtocolBindAdapterEx</i> returned NDIS_STATUS_PENDING,
    <i>ProtocolOpenAdapterCompleteEx</i> can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletebindadapterex">
    NdisCompleteBindAdapterEx</a> function to complete the binding operation. In this case, 
    <i>ProtocolOpenAdapterCompleteEx</i> passes 
    <b>NdisCompleteBindAdapterEx</b> the 
    <i>BindContext</i> handle that NDIS passed to 
    <i>ProtocolBindAdapterEx</i>. If the 
    <i>Status</i> parameter indicates an error, 
    <i>ProtocolOpenAdapterCompleteEx</i> can release binding resources that were set up in 
    <i>ProtocolBindAdapterEx</i>.

NDIS calls 
    <i>ProtocolOpenAdapterCompleteEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolOpenAdapterCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolOpenAdapterCompleteEx</i> function that is named "MyOpenAdapterCompleteEx", use the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX MyOpenAdapterCompleteEx;</pre>
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
 MyOpenAdapterCompleteEx(
    NDIS_HANDLE  ProtocolBindingContext,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_OPEN_ADAPTER_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscompletebindadapterex">NdisCompleteBindAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>
 

 

