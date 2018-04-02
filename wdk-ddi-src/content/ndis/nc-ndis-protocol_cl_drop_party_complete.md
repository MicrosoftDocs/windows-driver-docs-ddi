---
UID: NC:ndis.PROTOCOL_CL_DROP_PARTY_COMPLETE
title: PROTOCOL_CL_DROP_PARTY_COMPLETE
author: windows-driver-content
description: The ProtocolClDropPartyComplete function is used by connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolcldroppartycomplete.htm
old-project: netvista
ms.assetid: c916f379-393c-41d7-ab30-2f3181c3ada6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PROTOCOL_CL_DROP_PARTY_COMPLETE, ProtocolClDropPartyComplete, ProtocolClDropPartyComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_6586ee1a-9f7f-4125-966e-1f6df74b75df.xml, ndis/ProtocolClDropPartyComplete, netvista.protocolcldroppartycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClDropPartyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClDropPartyComplete (NDIS 5.1)) in Windows XP.
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
-	ProtocolClDropPartyComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_DROP_PARTY_COMPLETE callback


## -description


The 
  <i>ProtocolClDropPartyComplete</i> function is used by connection-oriented NDIS clients that set up
  multipoint connections. Such clients must have 
  <i>ProtocolClDropPartyComplete</i> functions to complete the asynchronous operations that they initiate with
  
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClDropPartyComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies the final status of the client-initiated drop-party operation, which can be one of the
     following:
     





#### NDIS_STATUS_SUCCESS

The party has been dropped. The 
       <i>NdisPartyHandle</i> that represented this party, which the client stored in its 
       <i>ProtocolPartyContext</i> area, is now invalid.



#### NDIS_STATUS_FAILURE

The given party was the last remaining on the client's multipoint VC. Therefore, the client
       should call 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a> to drop this
       party.


### -param ProtocolPartyContext [in]

Specifies the handle to the client's per-party context area, which the client originally supplied
     to NDIS either when it called 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>.


## -returns



None




## -remarks



A call to 
    <i>ProtocolClDropPartyComplete</i> indicates that the call manager has completed processing of the request
    initiated by the client's previous call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a>. 
    <i>ProtocolClDropPartyComplete</i> can either release the client-allocated per-party context area or
    prepare it for reuse in a subsequent call to 
    <b>NdisClAddParty</b>.

If the client is in the process of tearing down a multipoint VC that it created, 
    <i>ProtocolClDropPartyComplete</i> can call 
    <b>NdisClDropParty</b> with any valid 
    <i>NdisPartyHandle</i> to one of the remaining parties on the client's active multipoint VC. If only one
    more party remains on its multipoint VC, the client should drop that party by passing its 
    <i>NdisPartyHandle</i> to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClDropPartyComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClDropPartyComplete</i> function that is named "MyClDropPartyComplete", use the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_DROP_PARTY_COMPLETE MyClDropPartyComplete;</pre>
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
 MyClDropPartyComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolPartyContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561625">NdisClAddParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561629">NdisClDropParty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561674">NdisCmDropPartyComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563543">NdisMCmDropPartyComplete</a>



<a href="https://msdn.microsoft.com/be0fce3e-7308-42fa-b63a-4d5cfec7ea6c">ProtocolCmDropParty</a>
 

 

