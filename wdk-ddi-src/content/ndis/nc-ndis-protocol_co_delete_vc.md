---
UID: NC:ndis.PROTOCOL_CO_DELETE_VC
title: PROTOCOL_CO_DELETE_VC (ndis.h)
description: The ProtocolCoDeleteVc function is required.
old-location: netvista\protocolcodeletevc.htm
tech.root: netvista
ms.assetid: d761270f-bf77-441e-834c-9ac7fb3d350f
ms.date: 05/02/2018
keywords: ["PROTOCOL_CO_DELETE_VC callback function"]
ms.keywords: PROTOCOL_CO_DELETE_VC, PROTOCOL_CO_DELETE_VC callback, ProtocolCoDeleteVc, ProtocolCoDeleteVc callback function [Network Drivers Starting with Windows Vista], condis_protocol_ref_bd593797-8284-4b3e-980e-c5401776014f.xml, ndis/ProtocolCoDeleteVc, netvista.protocolcodeletevc
f1_keywords:
 - "ndis/ProtocolCoDeleteVc"
 - "ProtocolCoDeleteVc"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCoDeleteVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCoDeleteVc (NDIS   5.1)) in Windows XP.
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
- ProtocolCoDeleteVc
targetos: Windows
req.typenames: 
---

# PROTOCOL_CO_DELETE_VC callback function


## -description


The 
  <i>ProtocolCoDeleteVc</i> function is required. This function tears down the client's or call manager's
  state for an established virtual connection that is being closed by the original creator of that VC.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_DELETE_VC</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolVcContext [in]

Specifies the handle to the client's or call manager's per-VC context area. The protocol
     originally supplied this handle from its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


## -returns



<i>ProtocolCoDeleteVc</i> can return one of the following:

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
The protocol has released or prepared for reuse all the resources that it originally allocated
       for the VC.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The VC is still active and the protocol has outstanding operations pending on the VC so it could
       not be destroyed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The protocol failed the VC deletion for a driver-determined reason.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCoDeleteVc</i> is the reciprocal of the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function. In
    general, it releases any dynamic resources and structures that the call manager or client previously
    allocated to perform operations on the active VC.

When 
    <i>ProtocolCoDeleteVc</i> returns control with NDIS_STATUS_SUCCESS, the 
    <i>NdisVcHandle</i> that its 
    <i>ProtocolCoCreateVc</i> function stored in the area at 
    <i>ProtocolVcContext</i> becomes invalid.

<i>ProtocolCoDeleteVc</i> can return any driver-determined NDIS_STATUS_<i>XXX</i> to fail the deletion of the VC, but it 
    <u>cannot</u> return NDIS_STATUS_PENDING. Calls to 
    <i>ProtocolCoDeleteVc</i> are inherently synchronous in nature.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCoDeleteVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoDeleteVc</i> function that is named "MyCoDeleteVc", use the <b>PROTOCOL_CO_DELETE_VC</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_DELETE_VC MyCoDeleteVc;</pre>
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
    NDIS_HANDLE  ProtocolVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CO_DELETE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_DELETE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmdispatchincomingclosecall">
   NdisCmDispatchIncomingCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a>
 

 

