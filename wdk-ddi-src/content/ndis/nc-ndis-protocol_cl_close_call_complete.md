---
UID: NC:ndis.PROTOCOL_CL_CLOSE_CALL_COMPLETE
title: PROTOCOL_CL_CLOSE_CALL_COMPLETE
author: windows-driver-content
description: The ProtocolClCloseCallComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclclosecallcomplete.htm
old-project: netvista
ms.assetid: a7ba1ab2-04c9-45b5-a184-e1ad1448561a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolclclosecallcomplete, ProtocolClCloseCallComplete callback function [Network Drivers Starting with Windows Vista], ProtocolClCloseCallComplete, PROTOCOL_CL_CLOSE_CALL_COMPLETE, PROTOCOL_CL_CLOSE_CALL_COMPLETE, ndis/ProtocolClCloseCallComplete, condis_client_ref_a35e2fe4-8437-4c41-9ec1-13a8926108b5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	ProtocolClCloseCallComplete
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# PROTOCOL_CL_CLOSE_CALL_COMPLETE callback


## -description


The 
  <i>ProtocolClCloseCallComplete</i> function is used by connection-oriented NDIS clients. All
  connection-oriented NDIS clients must have 
  <i>ProtocolClCloseCallComplete</i> functions to complete the asynchronous operations that they initiate with
  
  <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CL_CLOSE_CALL_COMPLETE ProtocolClCloseCallComplete;

VOID ProtocolClCloseCallComplete(
  _In_     NDIS_STATUS Status,
  _In_     NDIS_HANDLE ProtocolVcContext,
  _In_opt_ NDIS_HANDLE ProtocolPartyContext
)
{ ... }
````


## -parameters




### -param Status [in]

Specifies the final status of the client's request to close this call, which can be one of the
     following:
     





#### NDIS_STATUS_SUCCESS

The call manager has successfully closed the call that existed on the given VC and deactivated
       the VC.



#### NDIS_STATUS_XXX

The call manager failed the request to close the call for some CM-determined reason, and NDIS
       propagated the status returned by its 
       <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a> function to
       the client.


### -param ProtocolVcContext [in]

Specifies the handle to the client's per-VC context area This is the handle that the client
     originally passed to NDIS with 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> or returned to NDIS from
     its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param ProtocolPartyContext [in, optional]

Specifies the handle to the client's per-party context area for the last remaining party on the
     client-created VC representing a multipoint connection. Otherwise, this parameter is <b>NULL</b>.


## -returns



None




## -remarks



If the given VC was created by the client and 
    <i>Status</i> is NDIS_STATUS_SUCCESS, the client can now do either of the following:

<ul>
<li>
Tear down its VC with 
      <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a> and release or prepare for
      reuse the context area(s) it allocated.

</li>
<li>
Reinitialize its per-VC context area and reuse its VC to make another connection with 
      <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.

</li>
</ul>
If the VC was created by the call manager, the client should consider the 
    <i>NdisVcHandle</i> invalid when 
    <i>ProtocolClCloseCallComplete</i> is called. The client must not make any further 
    <b>NdisCl/Co<i>Xxx</i></b> calls with this 
    <i>NdisVcHandle</i> . After 
    <i>ProtocolClCloseCallComplete</i> returns control, the call manager can delete its VC, thereby causing a
    call to the client's 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function. The
    call manager can even dispatch another incoming call on the VC that it created, thereby causing a call to
    the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
    ProtocolClIncomingCall</a> function.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClCloseCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
The <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CLOSE_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndiscmclosecallcomplete.md">NdisCmCloseCallComplete</a>



<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>



<a href="..\ndis\nf-ndis-ndismcmclosecallcomplete.md">NdisMCmCloseCallComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_CLOSE_CALL_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

