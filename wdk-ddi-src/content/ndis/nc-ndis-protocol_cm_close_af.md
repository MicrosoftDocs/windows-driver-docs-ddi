---
UID: NC:ndis.PROTOCOL_CM_CLOSE_AF
title: PROTOCOL_CM_CLOSE_AF (ndis.h)
description: The ProtocolCmCloseAf function is a required function that releases per-open resources for an address family that a call manager supports.Note  You must declare the function by using the PROTOCOL_CM_CLOSE_AF type.
old-location: netvista\protocolcmcloseaf.htm
tech.root: netvista
ms.assetid: a7a02813-62e4-49c5-abb6-a90f4e092b9f
ms.date: 05/02/2018
ms.keywords: PROTOCOL_CM_CLOSE_AF, PROTOCOL_CM_CLOSE_AF callback, ProtocolCmCloseAf, ProtocolCmCloseAf callback function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_bedb117e-f1a4-4faa-a6fb-c6b8a317c958.xml, ndis/ProtocolCmCloseAf, netvista.protocolcmcloseaf
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmCloseAf (NDIS 5.1))   in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmCloseAf (NDIS 5.1))   in Windows XP.
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
-	ProtocolCmCloseAf
product:
- Windows
targetos: Windows
req.typenames: 
---

# PROTOCOL_CM_CLOSE_AF callback function


## -description


The 
  <i>ProtocolCmCloseAf</i> function is a required function that releases per-open resources for an address
  family that a call manager supports.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CM_CLOSE_AF</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param CallMgrAfContext [in]

Specifies the handle to the call manager's per-AF context area, originally supplied to NDIS by the
     call manager's 
     <i>ProtocolCmOpenAf</i> function.


## -returns



<i>ProtocolCmCloseAf</i> returns the status of its operation(s) as one of the following:

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
Indicates that the call manager has successfully released or deactivated any resources that is
       allocated on behalf of the connection-oriented client that opened this instance of the address
       family.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the request to close the open instance of the address family will be completed
       asynchronously. The call manager must call 
       <a href="https://msdn.microsoft.com/1aeb2ca5-8c56-4a78-8cd5-a178efa9b014">
       NdisCmCloseAddressFamilyComplete</a> when all such operations have been completed.

</td>
</tr>
</table>
 




## -remarks



<i>ProtocolCmCloseAf</i> releases and/or deactivates any resources that were allocated by the call manager
    in its 
    <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function. The call
    manager also should undo any other actions it took on behalf of the connection-oriented client when the
    address family was opened by that client.

If there are any outstanding requests or connections still open on an address family stored in the 
    <i>CallMgrAfContext</i>, a call manager can respond to a client's request to close the address family in
    either of the following ways:

<ul>
<li>
The call manager can fail the request with NDIS_STATUS_NOT_ACCEPTED.

</li>
<li>
The call manager can return NDIS_STATUS_PENDING. After the client has closed all calls and
      deregistered all SAPs, the call manager can then close the address family and call 
      <b>NdisCmCloseAddressFamilyComplete</b> or 
      <a href="https://msdn.microsoft.com/be551557-06db-4fc9-bdcb-030e621e205a">
      NdisMCmCloseAddressFamilyComplete</a> to notify the client. This is the preferred response.

</li>
</ul>
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolCmCloseAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmCloseAf</i> function that is named "MyCmCloseAf", use the <b>PROTOCOL_CM_CLOSE_AF</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CM_CLOSE_AF MyCmCloseAf;</pre>
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
 MyCmCloseAf(
    NDIS_HANDLE  CallMgrAfContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CM_CLOSE_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_CLOSE_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/1aeb2ca5-8c56-4a78-8cd5-a178efa9b014">
   NdisCmCloseAddressFamilyComplete</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
 

 

