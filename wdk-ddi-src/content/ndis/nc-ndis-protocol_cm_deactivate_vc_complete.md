---
UID: NC:ndis.PROTOCOL_CM_DEACTIVATE_VC_COMPLETE
title: PROTOCOL_CM_DEACTIVATE_VC_COMPLETE (ndis.h)
description: The ProtocolCmDeactivateVcComplete function is a required function.
old-location: netvista\protocolcmdeactivatevccomplete.htm
tech.root: netvista
ms.assetid: 44ee0e3c-aee9-4e24-9e54-c57248b568b6
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_DEACTIVATE_VC_COMPLETE callback function"]
ms.keywords: PROTOCOL_CM_DEACTIVATE_VC_COMPLETE, PROTOCOL_CM_DEACTIVATE_VC_COMPLETE callback, ProtocolCmDeactivateVcComplete, ProtocolCmDeactivateVcComplete callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_ecf43479-8006-4170-9422-604236ede43a.xml, ndis/ProtocolCmDeactivateVcComplete, netvista.protocolcmdeactivatevccomplete
f1_keywords:
 - "ndis/ProtocolCmDeactivateVcComplete"
 - "ProtocolCmDeactivateVcComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolCmDeactivateVcComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolCmDeactivateVcComplete (NDIS 5.1)) in Windows XP.
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
- ProtocolCmDeactivateVcComplete
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_DEACTIVATE_VC_COMPLETE callback function


## -description


The 
  <i>ProtocolCmDeactivateVcComplete</i> function is a required function. 
  <i>ProtocolCmDeactivateVcComplete</i> completes the processing of a call manager-initiated request that the
  underlying miniport driver (and NDIS) deactivate a VC for which 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a> previously returned
  NDIS_STATUS_PENDING.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies the final status of the deactivation.


### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


## -remarks



NDIS usually calls 
    <i>ProtocolCmDeactivateVcComplete</i> in the context of the call manager's closing down a call on behalf
    of a connection-oriented client. The call manager typically calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a> function.
    Whenever 
    <b>NdisCmDeactivateVc</b> returns NDIS_STATUS_PENDING, NDIS subsequently calls its 
    <i>ProtocolCmDeactivateVcComplete</i> function.

That is, when the underlying connection-oriented miniport driver has deactivated the VC, NDIS calls 
    <i>ProtocolCmDeactivateVcComplete</i>. The final status of the deactivation is found in 
    <i>Status</i> . Possible values for the final status include, but are not limited to:



<i>ProtocolCmDeactivateVcComplete</i> performs whatever postprocessing is necessary to complete the
    deactivation of a virtual connection, such as setting flags in its state area to indicate that the
    connection is inactive or releasing dynamically allocated resources used while the VC is active.

Completion of the deactivation means that all call parameters for the VC used on activation are no
    longer valid. Any further use of the VC is prohibited except to reactivate it with a new set of call
    parameters.

Call managers should release any resources that were allocated for the VC activation and return
    control as quickly as possible. If the call manager previously returned NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a> function and
    all operations to close the call have been completed, 
    <i>ProtocolCmDeactivateVcComplete</i> should now call 
    <b>NdisCmCloseCallComplete</b>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmDeactivateVcComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDeactivateVcComplete</i> function that is named "MyCmDeactivateVcComplete", use the <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE MyCmDeactivateVcComplete;</pre>
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
 MyCmDeactivateVcComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  CallMgrVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_deactivate_vc">MiniportCoDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmclosecallcomplete">NdisCmCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a>
 

 

