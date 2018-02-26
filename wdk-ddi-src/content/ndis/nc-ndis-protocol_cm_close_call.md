---
UID: NC:ndis.PROTOCOL_CM_CLOSE_CALL
title: PROTOCOL_CM_CLOSE_CALL
author: windows-driver-content
description: The ProtocolCmCloseCall function is a required function that terminates an existing call and releases any resources that the call manager allocated for the call.Note  You must declare the function by using the PROTOCOL_CM_CLOSE_CALL type.
old-location: netvista\protocolcmclosecall.htm
old-project: netvista
ms.assetid: b5307e1b-3905-4e43-a0b0-0068ba18ef0d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PROTOCOL_CM_CLOSE_CALL, ProtocolCmCloseCall, ProtocolCmCloseCall callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_238e7e85-94af-4e1e-8eb2-04fc89515b4d.xml, ndis/ProtocolCmCloseCall, netvista.protocolcmclosecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmCloseCall (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmCloseCall (NDIS   5.1)) in Windows XP.
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
-	ProtocolCmCloseCall
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_CLOSE_CALL callback


## -description


The 
  <i>ProtocolCmCloseCall</i> function is a required function that terminates an existing call and releases any
  resources that the call manager allocated for the call.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_CLOSE_CALL</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CM_CLOSE_CALL ProtocolCmCloseCall;

NDIS_STATUS ProtocolCmCloseCall(
  _In_     NDIS_HANDLE CallMgrVcContext,
  _In_opt_ NDIS_HANDLE CallMgrPartyContext,
  _In_opt_ PVOID       CloseData,
  _In_opt_ UINT        Size
)
{ ... }
````


## -parameters




### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. This handle was provided to NDIS from the call managers 
     <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function.


### -param CallMgrPartyContext [in, optional]

Specifies the handle, if any, to a call manager-allocated context area in which the call manager
     maintain information about a party on a multipoint VC. This handle is <b>NULL</b> if the call being closed is
     not a multipoint call.


### -param CloseData [in, optional]

Pointer to a buffer containing connection-oriented client-specified data that should be sent
     across the connection before the call is terminated. This parameter is <b>NULL</b> if the underlying network
     medium does not support transfers of data when closing a connection.


### -param Size [in, optional]

Specifies the length, in bytes, of the buffer at 
     <i>CloseData</i>, zero if 
     <i>CloseData</i> is <b>NULL</b>.


## -returns



<i>ProtocolCmCloseCall</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager successfully terminated the call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager will complete the request to terminate the call asynchronously.
       When the call manager has completed all operations required to terminate the connection, it must then
       call 
       <a href="..\ndis\nf-ndis-ndiscmclosecallcomplete.md">NdisCmCloseCallComplete</a> to
       signal NDIS that the call has been closed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
Indicates that 
       <i>CloseData</i> was specified, but the underlying network medium does not support sending data
       concurrent with terminating a call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Indicates that the call manager could not terminate the call. The actual error returned can be a
       status propagated from another NDIS library routine.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmCloseCall</i> communicated with network control devices or other media-specific actors, as
    necessitated by its media, to terminate a connection between the local node and a remote node. If the
    call manager is required to communicate with network control devices (such as a networking switch) it
    should use a virtual connection to the network control device that it established in its 
    <i>ProtocolBindAdapterEx</i> function. Stand-alone call managers communicate to such network devices by
    calling 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>.
    Miniport drivers with integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, they transmit the data directly across the network.

If 
    <i>CloseData</i> is non-<b>NULL</b> and sending data at connection termination is supported by the media that
    this call manager handles, the call manager should transmit the data specified at 
    <i>CloseData</i> to the remote node before completing the call termination. If sending data concurrent
    with a connection being terminated is not supported, call managers should return
    NDIS_STATUS_INVALID_DATA.

If 
    <i>ProtocolCmCloseCall</i> is passed an explicit 
    <i>CallMgrPartyContext</i>, then the call being terminated is a multipoint VC, and the call manager must
    perform any necessary network communication with its networking hardware, as appropriate to its media
    type, to terminate the call as a multipoint call. The call manager must also free the memory that it
    allocated earlier, in 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>, for its
    per-party state that is pointed to by 
    <i>CallMgrPartyContext</i> . Failure to properly release, deallocate, or otherwise deactivate those
    resources causes a memory leak.

After the call has been terminated with the network, any close data has been sent, and any resources
    at 
    <i>CallMgrPartyContext</i> have been freed, the call manager must call 
    <a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>. This notifies NDIS
    and the underlying miniport driver, if any, to expect no further transfers on the given VC.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmCloseCall</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmCloseCall</i> function that is named "MyCmCloseCall", use the <b>PROTOCOL_CM_CLOSE_CALL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_CLOSE_CALL MyCmCloseCall;</pre>
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
 MyCmCloseCall(
    NDIS_HANDLE  CallMgrVcContext,
    NDIS_HANDLE  CallMgrPartyContext,
    PVOID  CloseData,
    UINT  Size
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_CLOSE_CALL</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_CLOSE_CALL</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_CLOSE_CALL callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

