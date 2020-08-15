---
UID: NC:ndis.PROTOCOL_CL_CLOSE_CALL_COMPLETE
title: PROTOCOL_CL_CLOSE_CALL_COMPLETE (ndis.h)
description: The ProtocolClCloseCallComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclclosecallcomplete.htm
tech.root: netvista
ms.assetid: a7ba1ab2-04c9-45b5-a184-e1ad1448561a
ms.date: 05/02/2018
keywords: ["PROTOCOL_CL_CLOSE_CALL_COMPLETE callback function"]
ms.keywords: PROTOCOL_CL_CLOSE_CALL_COMPLETE, PROTOCOL_CL_CLOSE_CALL_COMPLETE callback, ProtocolClCloseCallComplete, ProtocolClCloseCallComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_a35e2fe4-8437-4c41-9ec1-13a8926108b5.xml, ndis/ProtocolClCloseCallComplete, netvista.protocolclclosecallcomplete
f1_keywords:
 - "ndis/ProtocolClCloseCallComplete"
 - "ProtocolClCloseCallComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClCloseCallComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClCloseCallComplete (NDIS 5.1)) in Windows XP.
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
- ProtocolClCloseCallComplete
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_CLOSE_CALL_COMPLETE callback function


## -description


The 
  <i>ProtocolClCloseCallComplete</i> function is used by connection-oriented NDIS clients. All
  connection-oriented NDIS clients must have 
  <i>ProtocolClCloseCallComplete</i> functions to complete the asynchronous operations that they initiate with
  
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status 
[in]
Specifies the final status of the client's request to close this call, which can be one of the
     following:
     





#### NDIS_STATUS_SUCCESS

The call manager has successfully closed the call that existed on the given VC and deactivated
       the VC.



#### NDIS_STATUS_XXX

The call manager failed the request to close the call for some CM-determined reason, and NDIS
       propagated the status returned by its 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a> function to
       the client.


### -param ProtocolVcContext 
[in]
Specifies the handle to the client's per-VC context area This is the handle that the client
     originally passed to NDIS with 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscocreatevc">NdisCoCreateVc</a> or returned to NDIS from
     its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_create_vc">ProtocolCoCreateVc</a> function.


### -param ProtocolPartyContext 
[in, optional]
Specifies the handle to the client's per-party context area for the last remaining party on the
     client-created VC representing a multipoint connection. Otherwise, this parameter is <b>NULL</b>.


## -remarks



If the given VC was created by the client and 
    <i>Status</i> is NDIS_STATUS_SUCCESS, the client can now do either of the following:

<ul>
<li>
Tear down its VC with 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a> and release or prepare for
      reuse the context area(s) it allocated.

</li>
<li>
Reinitialize its per-VC context area and reuse its VC to make another connection with 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>.

</li>
</ul>
If the VC was created by the call manager, the client should consider the 
    <i>NdisVcHandle</i> invalid when 
    <i>ProtocolClCloseCallComplete</i> is called. The client must not make any further 
    <b>NdisCl/Co<i>Xxx</i></b> calls with this 
    <i>NdisVcHandle</i> . After 
    <i>ProtocolClCloseCallComplete</i> returns control, the call manager can delete its VC, thereby causing a
    call to the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a> function. The
    call manager can even dispatch another incoming call on the VC that it created, thereby causing a call to
    the client's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">
    ProtocolClIncomingCall</a> function.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClCloseCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCloseCallComplete</i> function that is named "MyClCloseCallComplete", use the <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_CLOSE_CALL_COMPLETE MyClCloseCallComplete;</pre>
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
 MyClCloseCallComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolVcContext,
    NDIS_HANDLE  ProtocolPartyContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclclosecall">NdisClCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisclmakecall">NdisClMakeCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscmclosecallcomplete">NdisCmCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscodeletevc">NdisCoDeleteVc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcmclosecallcomplete">NdisMCmCloseCallComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cl_incoming_call">ProtocolClIncomingCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_cm_close_call">ProtocolCmCloseCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_delete_vc">ProtocolCoDeleteVc</a>
 

 

