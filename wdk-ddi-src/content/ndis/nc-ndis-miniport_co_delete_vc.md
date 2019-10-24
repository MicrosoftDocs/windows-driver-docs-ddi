---
UID: NC:ndis.MINIPORT_CO_DELETE_VC
title: MINIPORT_CO_DELETE_VC (ndis.h)
description: The MiniportCoDeleteVc function is required for connection-oriented miniports.
old-location: netvista\miniportcodeletevc.htm
tech.root: netvista
ms.assetid: ed9b6ad1-059b-47d9-b1f7-10d498c5d2d4
ms.date: 05/02/2018
ms.keywords: MINIPORT_CO_DELETE_VC, MINIPORT_CO_DELETE_VC callback, MiniportCoDeleteVc, MiniportCoDeleteVc callback function [Network Drivers Starting with Windows Vista], condis_miniport_ref_4a19285a-9595-4ea0-bf86-ec69474a9716.xml, ndis/MiniportCoDeleteVc, netvista.miniportcodeletevc
ms.topic: callback
f1_keywords:
 - "ndis/MiniportCoDeleteVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoDeleteVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoDeleteVc (NDIS   5.1)) in Windows XP.
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
- MiniportCoDeleteVc
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_CO_DELETE_VC callback function


## -description


The 
  <i>MiniportCoDeleteVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoDeleteVc</i> indicates that a VC is being torn down and deleted by NDIS.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CO_DELETE_VC</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportVcContext [in]

Specifies the handle to a miniport driver-allocated context area in which the miniport driver
     maintains its per-VC state. The miniport driver supplied this handle to NDIS from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function.


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
Indicates that the miniport driver successfully freed all resources allocated for this
       VC.

</td>
</tr>
</table>
 




## -remarks



<i>MiniportCoDeleteVcmust</i> be written as a synchronous function and cannot, under any circumstances,
    return NDIS_STATUS_PENDING without causing a system-wide failure.

<i>MiniportCoDeleteVc</i> frees any resources allocated on a per-VC basis and stored in the context area 
    <i>MiniportVcContext</i> . The miniport driver must also free the 
    <i>MiniportVcContext</i> that is allocated in its 
    <i>MiniportCoCreateVc</i> function.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCoDeleteVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCoDeleteVc</i> function that is named "MyCoDeleteVc", use the <b>MINIPORT_CO_DELETE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_CO_DELETE_VC MyCoDeleteVc;</pre>
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
 MyCoDeleteVc(
    NDIS_HANDLE  MiniportVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_CO_DELETE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_DELETE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>
 

 

