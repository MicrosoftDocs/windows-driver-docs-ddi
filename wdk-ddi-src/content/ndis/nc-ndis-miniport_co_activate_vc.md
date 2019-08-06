---
UID: NC:ndis.MINIPORT_CO_ACTIVATE_VC
title: MINIPORT_CO_ACTIVATE_VC (ndis.h)
description: The MiniportCoActivateVc function is required for connection-oriented miniports.
old-location: netvista\miniportcoactivatevc.htm
tech.root: netvista
ms.assetid: 243a1236-4b8a-4f00-9f14-3142fa81c362
ms.date: 05/02/2018
ms.keywords: MINIPORT_CO_ACTIVATE_VC, MINIPORT_CO_ACTIVATE_VC callback, MiniportCoActivateVc, MiniportCoActivateVc callback function [Network Drivers Starting with Windows Vista], condis_miniport_ref_b93127ea-bac1-48d1-b7fd-3c7f40cbcbdb.xml, ndis/MiniportCoActivateVc, netvista.miniportcoactivatevc
ms.topic: callback
f1_keywords:
 - "ndis/MiniportCoActivateVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoActivateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoActivateVc (NDIS   5.1)) in Windows XP.
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
- MiniportCoActivateVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CO_ACTIVATE_VC callback function


## -description


The 
  <i>MiniportCoActivateVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoActivateVc</i> is called by NDIS to indicate to the miniport driver that a
  virtual connection is being activated.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_ACTIVATE_VC</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportVcContext [in]

Specifies the handle to a miniport driver-allocated context area in which the miniport driver
     maintains its per-VC state. The miniport driver supplied this handle to NDIS from its 
     <i>MiniportCoCreateVc</i> function.


### -param CallParameters [in, out]

Specifies the call parameters, as specified by the call manager, to be established for this VC. On
     output, the miniport driver returns altered call parameters if certain flags are set in the 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff545384(v=vs.85)">CO_CALL_PARAMETERS</a> structure.


## -returns



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
Indicates that the VC was activated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the miniport driver will complete the request to activate a VC asynchronously.
       When the miniport driver has finished with its operations, it must call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcoactivatevccomplete">
       NdisMCoActivateVcComplete</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call parameters specified at 
       <i>CallParameters</i> are invalid or illegal for the media type that this miniport
       driver supports.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the miniport driver could not activate the VC because it could not allocate all
       of the required resources that the miniport driver needs to maintain state information about the
       active VC.

</td>
</tr>
</table>
 




## -remarks



The miniport driver must validate the call parameters for this VC, as specified in 
    <i>CallParameters</i>, to verify that the adapter can support the requested call. If
    the requested call parameters cannot be satisfied, the miniport driver should fail the request with
    NDIS_STATUS_INVALID_DATA.

<i>MiniportCoActivateVc</i> can be called many times for a single VC in order to
    change the call parameters for an already active call. At every call, the miniport driver should validate
    the parameters and perform any processing as required by its adapter in order to satisfy the request.
    However, if it cannot set the given call parameters, 
    <i>MiniportCoActivateVc</i> must leave the VC in a usable state, because the
    connection-oriented client or a call manager can continue to send or receive data using the older call
    parameters.

If the ROUND_UP_FLOW or ROUND_DOWN_FLOW flags are set in the call parameters structure at 
    <i>CallParameters->MediaParameters->Flags</i>, the miniport driver has been
    requested to return the actual flow rate of the VC after the flow rate has been rounded according to the
    appropriate flag that has been set. If the miniport driver does change any of the call parameters because
    these flags have been set, it must return the actual call parameters in use for the VC at 
    <i>CallParameters</i>.

If the call parameters are acceptable, 
    <i>MiniportCoActivateVc</i> communicates with its adapter as necessary to prepare the
    adapter to receive or transmit data across the virtual connection (in other words, programming receive
    buffers).

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoActivateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoActivateVc</i> function that is named "MyCoActivateVc", use the <b>MINIPORT_CO_ACTIVATE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CO_ACTIVATE_VC MyCoActivateVc;</pre>
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
NDIS_STATUS
 MyCoActivateVc(
    NDIS_HANDLE  MiniportVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CO_ACTIVATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_ACTIVATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_deactivate_vc">MiniportCoDeactivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcoactivatevccomplete">NdisMCoActivateVcComplete</a>
 

 

