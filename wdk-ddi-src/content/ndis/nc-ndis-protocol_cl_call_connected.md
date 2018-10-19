---
UID: NC:ndis.PROTOCOL_CL_CALL_CONNECTED
title: PROTOCOL_CL_CALL_CONNECTED
author: windows-driver-content
description: The ProtocolClCallConnected function is used by connection-oriented NDIS clients that accept incoming calls.
old-location: netvista\protocolclcallconnected.htm
tech.root: netvista
ms.assetid: 675b2066-6a65-47cf-bde7-3c843f97c960
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CL_CALL_CONNECTED, PROTOCOL_CL_CALL_CONNECTED callback, ProtocolClCallConnected, ProtocolClCallConnected callback function [Network Drivers Starting with Windows Vista], condis_client_ref_ddc435b4-ff27-4ced-b513-9bba45302496.xml, ndis/ProtocolClCallConnected, netvista.protocolclcallconnected
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows XP.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolClCallConnected
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CL_CALL_CONNECTED callback function


## -description


The 
  <i>ProtocolClCallConnected</i> function is used by connection-oriented NDIS clients that accept incoming
  calls. Such clients must have 
  <i>ProtocolClCallConnected</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClCallConnected</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_CALL_CONNECTED</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolVcContext [in]

Specifies the client's handle to its per-VC context area. The client originally returned this
     handle to NDIS from its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function.


## -returns



None




## -remarks



When 
    <i>ProtocolClCallConnected</i> is called, the call manager has successfully completed the final handshake
    on an incoming call offer previously accepted by the client's 
    <i>ProtocolClIncomingCall</i> function, which already set up the call parameters for this connection at 
    <i>ProtocolVcContext</i> .

The call to 
    <i>ProtocolClCallConnected</i> indicates that data transfers, whether incoming or outgoing, now can be
    done on the VC. 
    <i>ProtocolClCallConnected</i> should ensure that the client is ready to make or accept transfers on the
    VC before it returns control.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClCallConnected</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCallConnected</i> function that is named "MyClCallConnected", use the <b>PROTOCOL_CL_CALL_CONNECTED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_CALL_CONNECTED MyClCallConnected;</pre>
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
 MyClCallConnected(
    NDIS_HANDLE  ProtocolVcContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_CALL_CONNECTED</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CALL_CONNECTED</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561661">NdisCmDispatchCallConnected</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561728">NdisCoSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562826">NdisMCmDispatchCallConnected</a>



<a href="https://msdn.microsoft.com/8a5922ac-b22b-444e-9ea0-3bb56e71ef33">ProtocolClIncomingCall</a>



<a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a>



<a href="https://msdn.microsoft.com/1755804c-d82f-465d-862f-8a2340516f8e">
   ProtocolCoReceiveNetBufferLists</a>
 

 

