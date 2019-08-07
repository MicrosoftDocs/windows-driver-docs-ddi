---
UID: NC:ndis.MINIPORT_CO_DEACTIVATE_VC
title: MINIPORT_CO_DEACTIVATE_VC (ndis.h)
description: The MiniportCoDeactivateVc function is required for connection-oriented miniports.
old-location: netvista\miniportcodeactivatevc.htm
tech.root: netvista
ms.assetid: 8c17cec8-d161-47cf-b886-bb8b8d957656
ms.date: 05/02/2018
ms.keywords: MINIPORT_CO_DEACTIVATE_VC, MINIPORT_CO_DEACTIVATE_VC callback, MiniportCoDeactivateVc, MiniportCoDeactivateVc callback function [Network Drivers Starting with Windows Vista], condis_miniport_ref_01461ff7-cd2e-466d-ab9a-7903484ecbc5.xml, ndis/MiniportCoDeactivateVc, netvista.miniportcodeactivatevc
ms.topic: callback
f1_keywords:
 - "ndis/MiniportCoDeactivateVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoDeactivateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoDeactivateVc (NDIS   5.1)) in Windows XP.
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
- MiniportCoDeactivateVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CO_DEACTIVATE_VC callback function


## -description


The 
  <i>MiniportCoDeactivateVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoDeactivateVc</i> is called by NDIS to indicate that a VC is being marked as unusable.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_DEACTIVATE_VC</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportVcContext [in]

Specified the handle to a miniport driver-allocated context area in which the miniport driver
     maintains state information per-VC. The miniport driver supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function.


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
Indicates that the miniport driver successfully halted any communication across the VC and
       marked it as unusable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the miniport driver will complete the request to halt the VC asynchronously. When
       the miniport driver has completed halting the VC, it must then call 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcodeactivatevccomplete">
       NdisMCoDeactivateVcComplete</a> to signal NDIS that this operation has been completed.

</td>
</tr>
</table>
 




## -remarks



<i>MiniportCoDeactivateVc</i> communicates with its network adapter to terminate all communication across
    this VC (in other words, deprogramming receive or send buffers on the adapter). The miniport driver
    should also mark the VC, it its context area, as being inactive to prevent any further communication
    across the VC.

There is not a one-to-one relationship between calls to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a> and 
    <i>MiniportCoDeactivateVc</i>. While NDIS may call 
    <i>MiniportCoActivateVc</i> multiple times on a single VC, only one call to 
    <i>MiniportCoDeactivateVc</i> is made to shut down a virtual connection. For example, a VC can be reused
    for different calls possibly causing multiple calls to 
    <i>MiniportCoActivateVc</i>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoDeactivateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoDeactivateVc</i> function that is named "MyCoDeactivateVc", use the <b>MINIPORT_CO_DEACTIVATE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CO_DEACTIVATE_VC MyCoDeactivateVc;</pre>
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
 MyCoDeactivateVc(
    NDIS_HANDLE  MiniportVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CO_DEACTIVATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_DEACTIVATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_co_activate_vc">MiniportCoActivateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcodeactivatevccomplete">NdisMCoDeactivateVcComplete</a>
 

 

