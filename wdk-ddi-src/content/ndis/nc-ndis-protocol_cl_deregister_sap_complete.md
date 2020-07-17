---
UID: NC:ndis.PROTOCOL_CL_DEREGISTER_SAP_COMPLETE
title: PROTOCOL_CL_DEREGISTER_SAP_COMPLETE (ndis.h)
description: The ProtocolClDeregisterSapComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclderegistersapcomplete.htm
tech.root: netvista
ms.assetid: 93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_DEREGISTER_SAP_COMPLETE callback function"]
ms.keywords: PROTOCOL_CL_DEREGISTER_SAP_COMPLETE, PROTOCOL_CL_DEREGISTER_SAP_COMPLETE callback, ProtocolClDeregisterSapComplete, ProtocolClDeregisterSapComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_7f2820e8-9dcb-494c-80f6-eac5aa96d869.xml, ndis/ProtocolClDeregisterSapComplete, netvista.protocolclderegistersapcomplete
f1_keywords:
 - "ndis/ProtocolClDeregisterSapComplete"
 - "ProtocolClDeregisterSapComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClDeregisterSapComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClDeregisterSapComplete (NDIS 5.1)) in Windows XP.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolClDeregisterSapComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_DEREGISTER_SAP_COMPLETE callback function


## -description


The 
  <i>ProtocolClDeregisterSapComplete</i> function is used by connection-oriented NDIS clients.
  Connection-oriented NDIS clients that accept incoming calls must have 
  <i>ProtocolClDeregisterSapComplete</i> functions to complete the asynchronous operations that they initiate
  with 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>. Otherwise, such a
  protocol driver's registered 
  <i>ProtocolClDeregisterSapComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies the final status of the client's request to deregister its SAP, which can be one of the
     following:
     





#### NDIS_STATUS_SUCCESS

The SAP was closed. The 
       <i>NdisSapHandle</i> that represented the client's previously registered SAP, which the client stored
       in its 
       <i>ProtocolSapContext</i> area, is now invalid.



#### NDIS_STATUS_FAILURE

NDIS had marked the state of the AF as "closing," so the associated SAP represented by the 
       <i>NdisSapHandle</i> was already released when the client's call to 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">
       NdisClDeregisterSap</a> occurred.



#### NDIS_STATUS_XXX

The call manager failed the request to close the SAP for some CM-determined reason, and NDIS
       propagated the status returned by its 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">
       ProtocolCmDeregisterSap</a> function to the client.


### -param ProtocolSapContext [in]

Specifies the client-supplied handle to its per-SAP context area, originally passed to NDIS with 
     <b>NdisClRegisterSap</b>. After the call manager has successfully deregistered this SAP, the client can
     release its context area or prepare this context area for reuse.


## -remarks



A call to 
    <i>ProtocolClDeregisterSapComplete</i> indicates that the client's preceding call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a> has been processed
    by the call manager.

Unless the call manager failed the deregistration for some CM-determined reason, the client should
    consider the 
    <i>NdisSapHandle</i> invalid when 
    <i>ProtocolClDeregisterSapComplete</i> is called. Consequently, 
    <i>ProtocolClDeregisterSapComplete</i> can release the per-SAP context area that the client allocated or
    prepare it for reuse in a subsequent call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClDeregisterSapComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClDeregisterSapComplete</i> function that is named "MyClDeregisterSapComplete", use the <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE MyClDeregisterSapComplete;</pre>
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
 MyClDeregisterSapComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolSapContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclderegistersap">NdisClDeregisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclregistersap">NdisClRegisterSap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmderegistersapcomplete">NdisCmDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmderegistersapcomplete">NdisMCmDeregisterSapComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_deregister_sap">ProtocolCmDeregisterSap</a>
 

 

