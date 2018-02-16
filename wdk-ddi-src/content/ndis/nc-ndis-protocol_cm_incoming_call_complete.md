---
UID: NC:ndis.PROTOCOL_CM_INCOMING_CALL_COMPLETE
title: PROTOCOL_CM_INCOMING_CALL_COMPLETE
author: windows-driver-content
description: The ProtocolCmIncomingCallComplete function is required.
old-location: netvista\protocolcmincomingcallcomplete.htm
old-project: netvista
ms.assetid: 353e929b-17c8-47e8-82fd-b646e93a5b9a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolcmincomingcallcomplete, ProtocolCmIncomingCallComplete callback function [Network Drivers Starting with Windows Vista], ProtocolCmIncomingCallComplete, PROTOCOL_CM_INCOMING_CALL_COMPLETE, PROTOCOL_CM_INCOMING_CALL_COMPLETE, ndis/ProtocolCmIncomingCallComplete, condis_call_manager_ref_0760b8c9-29b8-40ff-b8a9-03e4c4f792e2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolCmIncomingCallComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolCmIncomingCallComplete (NDIS 5.1)) in Windows XP.
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
-	ProtocolCmIncomingCallComplete
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# PROTOCOL_CM_INCOMING_CALL_COMPLETE callback


## -description


The 
  <i>ProtocolCmIncomingCallComplete</i> function is required. When NDIS calls this function, 
  <i>ProtocolCmIncomingCallComplete</i> indicates to the call manager that the connection-oriented client has
  finished processing of an incoming call offer that the call manager previously dispatched through 
  <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
  NdisCmDispatchIncomingCall</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CM_INCOMING_CALL_COMPLETE ProtocolCmIncomingCallComplete;

VOID ProtocolCmIncomingCallComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         CallMgrVcContext,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters




### -param Status [in]

Indicates the final status of the operation to dispatch an incoming call to a connection-oriented
     client.


### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param CallParameters [in]

Pointer to the call parameters as specified by the call manager in the call to 
     <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>.
     The signaling protocol determines which call parameters, if any, the call manager can change.


## -returns



None




## -remarks



When the connection-oriented client has completed processing of an incoming connection offer that the
    call manager dispatched to it, this routine will be called if 
    <b>NdisCmDispatchIncomingCall</b> returned NDIS_STATUS_PENDING. The final status of the incoming call is
    found in 
    <i>Status</i>. Possible values for 
    <i>Status</i> include, but are not limited to:



If the client accepts the incoming call, the call manager should send signaling message(s) to indicate
    to the calling entity that the call has been accepted. If the client does not accept the call, the call
    manager should send signaling message(s) to indicate that the call has been rejected.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmIncomingCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmIncomingCallComplete</i> function that is named "MyCmIncomingCallComplete", use the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_INCOMING_CALL_COMPLETE MyCmIncomingCallComplete;</pre>
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
 MyCmIncomingCallComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_INCOMING_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_INCOMING_CALL_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

