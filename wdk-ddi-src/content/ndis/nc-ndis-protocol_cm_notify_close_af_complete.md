---
UID: NC:ndis.PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE
title: PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE (ndis.h)
description: The ProtocolCmNotifyCloseAfComplete function indicates that a client has completed the closing of an address family (AF) that a stand-alone call manager or miniport call manager (MCM) started by calling the NdisCmNotifyCloseAddressFamily or NdisMCmNotifyCloseAddressFamily function, respectively.Note  You must declare the function by using the PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocolcmnotifycloseafcomplete.htm
tech.root: netvista
ms.assetid: c5bdedee-dacd-4f4d-a3d1-f1cb71a68001
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE, PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE callback, ProtocolCmNotifyCloseAfComplete, ProtocolCmNotifyCloseAfComplete callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_f10e7b00-20f8-4bb0-a4c0-94855572fc08.xml, ndis/ProtocolCmNotifyCloseAfComplete, netvista.protocolcmnotifycloseafcomplete
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- ProtocolCmNotifyCloseAfComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE callback function


## -description


The 
  <i>ProtocolCmNotifyCloseAfComplete</i> function indicates that a client has completed the closing of an
  address family (AF) that a stand-alone call manager or miniport call manager (MCM) started by calling the 
  <a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
  NdisCmNotifyCloseAddressFamily</a> or 
  <a href="https://msdn.microsoft.com/47b0b1da-e29b-45cc-921b-69d630670b44">
  NdisMCmNotifyCloseAddressFamily</a> function, respectively.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrAfContext [in]

A handle to the call manager's AF context area that the call manager supplied to NDIS in the 
     <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function.


### -param Status [in]

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
    <a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
    NdisCmNotifyCloseAddressFamily</a> function before unbinding. When a miniport call manager (MCM) halts
    a miniport adapter, the MCM must call the 
    <a href="https://msdn.microsoft.com/47b0b1da-e29b-45cc-921b-69d630670b44">
    NdisMCmNotifyCloseAddressFamily</a> function.

If 
    <b>NdisCmNotifyCloseAddressFamily</b> or 
    <b>NdisMCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>ProtocolCmNotifyCloseAfComplete</i> after the client completes the AF close operation.

NDIS calls 
    <i>ProtocolCmNotifyCloseAfComplete</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmNotifyCloseAfComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
 MyCmNotifyCloseAfComplete(
    NDIS_HANDLE  CallMgrAfContext,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_NOTIFY_CLOSE_AF_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
   NdisCmNotifyCloseAddressFamily</a>



<a href="https://msdn.microsoft.com/47b0b1da-e29b-45cc-921b-69d630670b44">
   NdisMCmNotifyCloseAddressFamily</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
 

 

