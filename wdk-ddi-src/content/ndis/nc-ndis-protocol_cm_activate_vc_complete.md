---
UID: NC:ndis.PROTOCOL_CM_ACTIVATE_VC_COMPLETE
title: PROTOCOL_CM_ACTIVATE_VC_COMPLETE (ndis.h)
description: The ProtocolCmActivateVcComplete function is required.
old-location: netvista\protocolcmactivatevccomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PROTOCOL_CM_ACTIVATE_VC_COMPLETE callback function"]
ms.keywords: PROTOCOL_CM_ACTIVATE_VC_COMPLETE, PROTOCOL_CM_ACTIVATE_VC_COMPLETE callback, ProtocolCmActivateVcComplete, ProtocolCmActivateVcComplete callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_2a632e5a-975c-44a2-8b30-088c128561c2.xml, ndis/ProtocolCmActivateVcComplete, netvista.protocolcmactivatevccomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolCmActivateVcComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolCmActivateVcComplete (NDIS 5.1)) in Windows XP.
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
 - PROTOCOL_CM_ACTIVATE_VC_COMPLETE
 - ndis/PROTOCOL_CM_ACTIVATE_VC_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - PROTOCOL_CM_ACTIVATE_VC_COMPLETE
---

# PROTOCOL_CM_ACTIVATE_VC_COMPLETE callback function


## -description

The 
  <i>ProtocolCmActivateVcComplete</i> function is required. This function indicates to the call manager that a
  previous call to 
  <b>NdisCoActivateVc</b> has been completed by the miniport driver.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_ACTIVATE_VC_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param Status [in]


Specifies the final status, as indicated by the miniport driver, of the request by the call
     manager to activate a VC.

### -param CallMgrVcContext [in]


Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle from its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.

### -param CallParameters [in]


Pointer to the call parameters as specified by the call manager in a call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a>.

## -remarks

When other network components have completed their operations for activating a virtual connection,
    initiated when the call manager called 
    <b>NdisCmActivateVc</b>, NDIS notifies the call manager that the VC has been activated by calling its 
    <i>ProtocolCmActivateVcComplete</i> function. The status of the activation is found in 
    <i>Status</i> . Possible values for 
    <i>Status</i> include, but are not limited to:



<i>ProtocolCmActivateVcComplete</i> must check the status returned in 
    <i>Status</i> to ensure that the virtual connection has been activated successfully. The call manager 
    <u>must not</u> attempt to communicate over the virtual connection if 
    <i>Status</i> is not NDIS_STATUS_SUCCESS.

Call managers must complete any processing required by their network media to ensure that the virtual
    connection is ready for data transmission before returning control to NDIS.

If the call manager specified either ROUND_UP_FLOW or ROUND_DOWN_FLOW in the 
    <i>CallParameters</i> ->     
    <b>MediaParameters->Flags</b>, the call parameters returned in 
    <i>CallParameters</i> can have been changed by the miniport driver. Call managers should examine the call
    parameters that were returned to ensure proper operation. If the new call parameters are unsatisfactory,
    the call manager should either call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a> again with new call
    parameters or deactivate the VC with 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmActivateVcComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmActivateVcComplete</i> function that is named "MyCmActivateVcComplete", use the <b>PROTOCOL_CM_ACTIVATE_VC_COMPLETE</b> type as shown in this code example:


```
PROTOCOL_CM_ACTIVATE_VC_COMPLETE MyCmActivateVcComplete;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCmActivateVcComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}
```

The <b>PROTOCOL_CM_ACTIVATE_VC_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_ACTIVATE_VC_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmactivatevc">NdisCmActivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdeactivatevc">NdisCmDeactivateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_make_call">ProtocolCmMakeCall</a>

