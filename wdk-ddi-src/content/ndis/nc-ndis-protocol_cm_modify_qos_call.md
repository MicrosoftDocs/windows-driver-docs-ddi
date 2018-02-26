---
UID: NC:ndis.PROTOCOL_CM_MODIFY_QOS_CALL
title: PROTOCOL_CM_MODIFY_QOS_CALL
author: windows-driver-content
description: The ProtocolCmModifyCallQoS function is required.
old-location: netvista\protocolcmmodifycallqos.htm
old-project: netvista
ms.assetid: 24523677-9f5a-4109-8484-95883a4d1bbf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PROTOCOL_CM_MODIFY_QOS_CALL, ProtocolCmModifyCallQoS, ProtocolCmModifyCallQoS callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_208d4e81-1f4f-46e9-9b78-7724504b68bc.xml, ndis/ProtocolCmModifyCallQoS, netvista.protocolcmmodifycallqos
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmModifyCallQoS (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmModifyCallQoS (NDIS   5.1)) in Windows XP.
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
-	ProtocolCmModifyCallQoS
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_MODIFY_QOS_CALL callback


## -description


The 
  <i>ProtocolCmModifyCallQoS</i> function is required. 
  <i>ProtocolCmModifyCallQoS</i> is called by NDIS when a connection-oriented client requests that the call
  parameters be changed for an existing virtual connection (VC). If the underlying network medium does not
  support QoS, 
  <i>ProtocolCmModifyQoS</i> should simply return NDIS_STATUS_NOT_SUPPORTED.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CM_MODIFY_QOS_CALL ProtocolCmModifyCallQoS;

NDIS_STATUS ProtocolCmModifyCallQoS(
  _In_ NDIS_HANDLE         CallMgrVcContext,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters




### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS for its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param CallParameters [in]

Pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure that contains
     the new call parameters, as specified by a connection-oriented client, for the VC.


## -returns



<i>ProtocolCmModifyQoS</i> returns the status of its operation(s) as one of the following values:

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
Indicates that the call manager successfully changed the parameters of the call with the network
       to the call parameters specified at 
       <i>CallParameters</i> .

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to modify the call parameters
       asynchronously. When the call manager has completed all operations necessary to modify the call
       parameters, it must call 
       <a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">
       NdisCmModifyCallQoSComplete</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager could not change the call parameters of the VC because
       dynamically allocated resources were not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager was unable to change the call parameters of the VC because the
       call parameters provided at 
       <i>CallParameters</i> were illegal or invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call parameters could not be set to the call parameters provided because of a
       failure in the network or in another connection-oriented network component.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmModifyQoS</i> communicates with network control devices or other media-specific agents, as
    necessitated by its media, to modify the media-specific call parameters for an established virtual
    connection. If the call manager is required to communicate with network control agents (in other words, a
    networking switch) it should use a virtual connection to the network control agents that it established
    in its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function.
    Stand-alone call managers communicated to the network agents by calling 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>.
    Miniport drivers with integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, such a driver simply transfers the data over the network to the
    target network agent.

After communicating with the network and if the changes were successful, the call manager must then
    call 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a> with the new call
    parameters. This notifies NDIS and/or the connection-oriented miniport driver that the call parameters
    have changed and provides the miniport driver with an opportunity to validate those parameters.

If either the network cannot accept the new call parameters or the underlying miniport driver cannot
    accept the parameters, the call manager must restore the virtual connection to the state that existed
    before any modifications were attempted, and return NDIS_STATUS_FAILURE.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmModifyCallQoS</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmModifyCallQoS</i> function that is named "MyCmModifyCallQoS", use the <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_MODIFY_QOS_CALL MyCmModifyCallQoS;</pre>
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
 MyCmModifyCallQoS(
    NDIS_HANDLE  CallMgrVcContext,
    PCO_CALL_PARAMETERS  CallParameters
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_MODIFY_QOS_CALL</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>



<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">NdisCmModifyCallQoSComplete</a>



<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_MODIFY_QOS_CALL callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

