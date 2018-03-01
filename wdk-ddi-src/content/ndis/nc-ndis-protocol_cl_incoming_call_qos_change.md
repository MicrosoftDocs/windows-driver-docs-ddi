---
UID: NC:ndis.PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
title: PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE
author: windows-driver-content
description: The ProtocolClIncomingCallQoSChange function is used by connection-oriented clients on networks that support dynamic quality-of-service.
old-location: netvista\protocolclincomingcallqoschange.htm
old-project: netvista
ms.assetid: ca9953f4-35db-4acb-b0ea-887156b4f6ee
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE, ProtocolClIncomingCallQoSChange, ProtocolClIncomingCallQoSChange callback function [Network Drivers Starting with Windows Vista], condis_client_ref_09f3fdc8-cdc0-4b49-82c2-bd5816c9d5a9.xml, ndis/ProtocolClIncomingCallQoSChange, netvista.protocolclincomingcallqoschange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClIncomingCallQoSChange (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClIncomingCallQoSChange (NDIS 5.1)) in Windows XP.
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
-	ProtocolClIncomingCallQoSChange
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE callback


## -description


The 
  <i>ProtocolClIncomingCallQoSChange</i> function is used by connection-oriented clients on networks that
  support dynamic quality-of-service. Such clients must have 
  <i>ProtocolClIncomingCallQoSChange</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClIncomingCallQoSChange</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE ProtocolClIncomingCallQoSChange;

VOID ProtocolClIncomingCallQoSChange(
  _In_ NDIS_HANDLE         ProtocolVcContext,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters




### -param ProtocolVcContext [in]

Specifies the handle to the client's per-VC context area for the VC on which a request to modify
     the quality of service has come in over the network.


### -param CallParameters [in]

Pointer to a buffer, formatted as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure, that contains
     the new QoS specification.


## -returns



None




## -remarks



A call to 
    <i>ProtocolClIncomingCallQoSChange</i> indicates to the client that a remote peer has requested a change
    in the quality of service on this call. The new quality of service is described at 
    <i>CallParameters</i> . The client can accept the requested change by simply returning control. Otherwise,
    
    <i>ProtocolClIncomingCallQoSChange</i> should tear down the call with 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClIncomingCallQoSChange</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClIncomingCallQoSChange</i> function that is named "MyClIncomingCallQoSChange", use the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE MyClIncomingCallQoSChange;</pre>
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
 MyClIncomingCallQoSChange(
    NDIS_HANDLE  ProtocolVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_INCOMING_CALL_QOS_CHANGE callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

