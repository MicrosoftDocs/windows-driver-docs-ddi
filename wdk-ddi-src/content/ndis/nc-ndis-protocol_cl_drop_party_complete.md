---
UID: NC:ndis.PROTOCOL_CL_DROP_PARTY_COMPLETE
title: PROTOCOL_CL_DROP_PARTY_COMPLETE
author: windows-driver-content
description: The ProtocolClDropPartyComplete function is used by connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolcldroppartycomplete.htm
old-project: netvista
ms.assetid: c916f379-393c-41d7-ab30-2f3181c3ada6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolcldroppartycomplete, ProtocolClDropPartyComplete callback function [Network Drivers Starting with Windows Vista], ProtocolClDropPartyComplete, PROTOCOL_CL_DROP_PARTY_COMPLETE, PROTOCOL_CL_DROP_PARTY_COMPLETE, ndis/ProtocolClDropPartyComplete, condis_client_ref_6586ee1a-9f7f-4125-966e-1f6df74b75df.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
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
  
  <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClDropPartyComplete</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CL_DROP_PARTY_COMPLETE ProtocolClDropPartyComplete;

VOID ProtocolClDropPartyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE ProtocolPartyContext
)
{ ... }
````


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
       <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a> to drop this
       party.


### -param ProtocolPartyContext [in]

Specifies the handle to the client's per-party context area, which the client originally supplied
     to NDIS either when it called 
     <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> or 
     <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.


## -returns


None



## -remarks


A call to 
    <i>ProtocolClDropPartyComplete</i> indicates that the call manager has completed processing of the request
    initiated by the client's previous call to 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>. 
    <i>ProtocolClDropPartyComplete</i> can either release the client-allocated per-party context area or
    prepare it for reuse in a subsequent call to 
    <b>NdisClAddParty</b>.

If the client is in the process of tearing down a multipoint VC that it created, 
    <i>ProtocolClDropPartyComplete</i> can call 
    <b>NdisClDropParty</b> with any valid 
    <i>NdisPartyHandle</i> to one of the remaining parties on the client's active multipoint VC. If only one
    more party remains on its multipoint VC, the client should drop that party by passing its 
    <i>NdisPartyHandle</i> to 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>ProtocolClDropPartyComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
</table></span></div>Then, implement your function as follows:
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
</table></span></div>The <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<a href="..\ndis\nf-ndis-ndiscmdroppartycomplete.md">NdisCmDropPartyComplete</a>

<a href="..\ndis\nf-ndis-ndismcmdroppartycomplete.md">NdisMCmDropPartyComplete</a>

<mshelp:link keywords="netvista.ndisfreetonpagedlookasidelist" tabindex="0"><b>
   NdisFreeToNPagedLookasideList</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>

<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>

<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>

<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>

<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>

<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_DROP_PARTY_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

