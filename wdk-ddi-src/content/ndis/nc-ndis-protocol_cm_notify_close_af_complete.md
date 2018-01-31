---
UID: NC:ndis.PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE
title: PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE
author: windows-driver-content
description: The ProtocolCmNotifyCloseAfComplete function indicates that a client has completed the closing of an address family (AF) that a stand-alone call manager or miniport call manager (MCM) started by calling the NdisCmNotifyCloseAddressFamily or NdisMCmNotifyCloseAddressFamily function, respectively.Note  You must declare the function by using the PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocolcmnotifycloseafcomplete.htm
old-project: netvista
ms.assetid: c5bdedee-dacd-4f4d-a3d1-f1cb71a68001
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolcmnotifycloseafcomplete, ProtocolCmNotifyCloseAfComplete callback function [Network Drivers Starting with Windows Vista], ProtocolCmNotifyCloseAfComplete, PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE, PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE, ndis/ProtocolCmNotifyCloseAfComplete, condis_call_manager_ref_f10e7b00-20f8-4bb0-a4c0-94855572fc08.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	ProtocolCmNotifyCloseAfComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE callback


## -description


The 
  <i>ProtocolCmNotifyCloseAfComplete</i> function indicates that a client has completed the closing of an
  address family (AF) that a stand-alone call manager or miniport call manager (MCM) started by calling the 
  <mshelp:link keywords="netvista.ndiscmnotifycloseaddressfamily" tabindex="0"><b>
  NdisCmNotifyCloseAddressFamily</b></mshelp:link> or 
  <mshelp:link keywords="netvista.ndismcmnotifycloseaddressfamily" tabindex="0"><b>
  NdisMCmNotifyCloseAddressFamily</b></mshelp:link> function, respectively.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE ProtocolCmNotifyCloseAfComplete;

VOID ProtocolCmNotifyCloseAfComplete(
  _In_ NDIS_HANDLE CallMgrAfContext,
  _In_ NDIS_STATUS Status
)
{ ... }
````


## -parameters




#### - CallMgrAfContext [in]

A handle to the call manager's AF context area that the call manager supplied to NDIS in the 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


#### - Status [in]

The clients final status for the AF close notification. 
     <i>Status</i> can be one of the following:
     




#### NDIS_STATUS_SUCCESS

The client successfully closed its address family.


#### NDIS_STATUS_XXX

The client failed the request for some driver-determined reason.


## -returns


None



## -remarks


The 
    <i>ProtocolCmNotifyCloseAfComplete</i> function is required for CoNDIS call managers.

If a stand-alone call manager will unbind from an underlying miniport adapter, the call manager must
    call the 
    <mshelp:link keywords="netvista.ndiscmnotifycloseaddressfamily" tabindex="0"><b>
    NdisCmNotifyCloseAddressFamily</b></mshelp:link> function before unbinding. When a miniport call manager (MCM) halts
    a miniport adapter, the MCM must call the 
    <mshelp:link keywords="netvista.ndismcmnotifycloseaddressfamily" tabindex="0"><b>
    NdisMCmNotifyCloseAddressFamily</b></mshelp:link> function.

If 
    <b>NdisCmNotifyCloseAddressFamily</b> or 
    <b>NdisMCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>ProtocolCmNotifyCloseAfComplete</i> after the client completes the AF close operation.

NDIS calls 
    <i>ProtocolCmNotifyCloseAfComplete</i> at IRQL &lt;= DISPATCH_LEVEL.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>ProtocolCmNotifyCloseAfComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmNotifyCloseAfComplete</i> function that is named "MyCmNotifyCloseAfComplete", use the <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE MyCmNotifyCloseAfComplete;</pre>
</td>
</tr>
</table></span></div>Then, implement your function as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyCmNotifyCloseAfComplete(
    NDIS_HANDLE  CallMgrAfContext,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<mshelp:link keywords="netvista.ndismcmnotifycloseaddressfamily" tabindex="0"><b>
   NdisMCmNotifyCloseAddressFamily</b></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>

<mshelp:link keywords="netvista.ndiscmnotifycloseaddressfamily" tabindex="0"><b>
   NdisCmNotifyCloseAddressFamily</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

