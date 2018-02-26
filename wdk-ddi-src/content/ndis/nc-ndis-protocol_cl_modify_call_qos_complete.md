---
UID: NC:ndis.PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE
title: PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE
author: windows-driver-content
description: The ProtocolClModifyCallQoSComplete function is used by connection-oriented NDIS clients that can modify the quality of service on a connection dynamically.
old-location: netvista\protocolclmodifycallqoscomplete.htm
old-project: netvista
ms.assetid: 0d925862-49af-4579-b877-c9a033e73be0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE, ProtocolClModifyCallQoSComplete, ProtocolClModifyCallQoSComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_19bed505-8cde-44c3-bee1-dd5cc7a26526.xml, ndis/ProtocolClModifyCallQoSComplete, netvista.protocolclmodifycallqoscomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClModifyCallQoSComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClModifyCallQoSComplete (NDIS 5.1)) in Windows XP.
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
-	ProtocolClModifyCallQoSComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE callback


## -description


The 
  <i>ProtocolClModifyCallQoSComplete</i> function is used by connection-oriented NDIS clients that can modify
  the quality of service on a connection dynamically. Such clients must have 
  <i>ProtocolClModifyCallQoSComplete</i> functions to complete the asynchronous operations that they initate
  with 
  <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>. Otherwise, such a
  protocol driver's registered 
  <i>ProtocolClModifyCallQoSComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE ProtocolClModifyCallQoSComplete;

VOID ProtocolClModifyCallQoSComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         ProtocolVcContext,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters




### -param Status [in]

Specifies the final status of the client's asynchronous request to modify the call parameters for
     this VC as one of the following:
     





#### NDIS_STATUS_SUCCESS

The QoS was modified as requested by the client.



#### NDIS_STATUS_RESOURCES

NDIS or the call manager could not modify the QoS because one of them could not allocate
       sufficient resources dynamically.



#### NDIS_STATUS_INVALID_DATA

The call parameters that the client supplied to 
       <b>NdisClModifyCallQoS</b> were invalid.



#### NDIS_STATUS_FAILURE

The call manager could not change the QoS because of a failure on the network or in another
       connection-oriented network component.



#### NDIS_STATUS_XXX

The call manager failed to change the QoS, and NDIS propagated the CM-determined failure status
       to the client.


### -param ProtocolVcContext [in]

Specifies the handle to the client's per-VC context area, which the client originally supplied to
     NDIS when it called 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> to set up the VC for its
     outgoing call request or from its 
     <i>ProtocolCoCreateVc</i> function if the client accepted an incoming call on this VC.


### -param CallParameters [in]

Pointer to a buffered CO_CALL_PARAMETERS structure containing the client-specified QoS change it
     requested, or, possibly, the original QoS for this VC established when the connection was activated,
     which the call manager has restored.


## -returns



None




## -remarks



A call to 
    <i>ProtocolClModifyCallQoSComplete</i> indicates that the call manager has completed processing of a
    client-initiated request to change the quality of service on an active VC. For example, if the underlying
    network medium supports dynamic QoS changes, a client can request modifications at any time on an active
    VC.

If the client's call to 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a> succeeds, 
    <i>ProtocolClModifyCallQoSComplete</i> can accept the QoS change by simply returning control. Otherwise, 
    <i>ProtocolClModifyCallQoSComplete</i> can engage in further negotiation with the call manager as long as
    the client's developer places some reasonable limit on the number of possible renegotiations.
    Alternatively, 
    <i>ProtocolClModifyCallQoSComplete</i> can simply tear down the call with 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a> whenever the call manager
    rejects a request to change the QoS and the previously established QoS has become unacceptable to the
    client.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClModifyCallQoSComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClModifyCallQoSComplete</i> function that is named "MyClModifyCallQoSComplete", use the <b>PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE MyClModifyCallQoSComplete;</pre>
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
 MyClModifyCallQoSComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndismcmmodifycallqoscomplete.md">NdisMCmModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>



<a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">NdisCmModifyCallQoSComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_MODIFY_CALL_QOS_COMPLETE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

