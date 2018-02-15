---
UID: NC:ndis.PROTOCOL_CL_INCOMING_DROP_PARTY
title: PROTOCOL_CL_INCOMING_DROP_PARTY
author: windows-driver-content
description: The ProtocolClIncomingDropParty function is used by connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolclincomingdropparty.htm
old-project: netvista
ms.assetid: 3815ca4b-f4bc-4de9-a28a-5d3ee20bcdd8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolclincomingdropparty, ProtocolClIncomingDropParty callback function [Network Drivers Starting with Windows Vista], ProtocolClIncomingDropParty, PROTOCOL_CL_INCOMING_DROP_PARTY, PROTOCOL_CL_INCOMING_DROP_PARTY, ndis/ProtocolClIncomingDropParty, condis_client_ref_ac4b9f43-23f6-4300-8110-1589cecffe21.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClIncomingDropParty (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClIncomingDropParty (NDIS 5.1)) in Windows XP.
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
-	ProtocolClIncomingDropParty
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# PROTOCOL_CL_INCOMING_DROP_PARTY callback


## -description


The 
  <i>ProtocolClIncomingDropParty</i> function is used by connection-oriented NDIS clients that set up
  multipoint connections. Such clients must have 
  <i>ProtocolClIncomingDropParty</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClIncomingDropParty</i> function can simply return control.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_INCOMING_DROP_PARTY</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CL_INCOMING_DROP_PARTY ProtocolClIncomingDropParty;

VOID ProtocolClIncomingDropParty(
  _In_ NDIS_STATUS DropStatus,
  _In_ NDIS_HANDLE ProtocolPartyContext,
  _In_ PVOID       CloseData,
  _In_ UINT        Size
)
{ ... }
````


## -parameters




### -param DropStatus [in]

Indicates the reason for the party to be dropped. Usually, this is NDIS_STATUS_SUCCESS if the
     party on the remote note initiated a close of its connection, but it could be any CM-determined status
     if the call manager initiated this drop-party operation due to network problems that it
     discovered.


### -param ProtocolPartyContext [in]

Specifies the handle to the client's per-party context area for the party to be dropped. The
     client originally supplied this handle to NDIS when it called 
     <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> or 
     <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>.


### -param CloseData [in]

Pointer to a buffer containing a protocol-specific close message, possibly one supplied by the
     remote client that the call manager received over the network, or this parameter can be <b>NULL</b>. 
     

When 
     <i>DropStatus</i> is NDIS_STATUS_SUCCESS, this parameter is <b>NULL</b> if the underlying network medium does
     not support transfers of data when closing a connection. However, any particular call manager might
     define a structure to pass additional diagnostic information to its clients on drop-party operations
     caused by problems on the network.


### -param Size [in]

Specifies the length, in bytes, of the buffer at 
     <i>CloseData</i>, zero if 
     <i>CloseData</i> is <b>NULL</b>.


## -returns



None




## -remarks



A call to 
    <i>ProtocolClIncomingDropParty</i> indicates that the one of the following has occurred:

<ul>
<li>
The call manager has received a request over the network to close an established connection,
      identified by the 
      <i>NdisPartyHandle</i> that the client stored in its per-party context area at 
      <i>ProtocolPartyContext</i> .

</li>
<li>
The call manager has detected that network problems will prevent further data transfers on the
      established connection.

</li>
</ul>
In either case, 
    <i>ProtocolClIncomingDropParty</i> should carry out any protocol-determined operations for dropping the
    party from the client's multipoint VC. 
    <i>ProtocolClIncomingDropParty</i> must call 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a> or, if this is the last
    remaining party on the client's multipoint VC, 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.

<i>ProtocolClIncomingDropParty</i> should consider the 
    <i>NdisPartyHandle</i> that the client obtained from 
    <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> or 
    <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> invalid. 
    <i>ProtocolClIncomingDropParty</i> can either release the client's per-party context area or prepare it
    for reuse in a subsequent call to 
    <b>NdisClAddParty</b>.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClIncomingDropParty</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClIncomingDropParty</i> function that is named "MyClIncomingDropParty", use the <b>PROTOCOL_CL_INCOMING_DROP_PARTY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_INCOMING_DROP_PARTY MyClIncomingDropParty;</pre>
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
 MyClIncomingDropParty(
    NDIS_STATUS  DropStatus,
    NDIS_HANDLE  ProtocolPartyContext,
    PVOID  CloseData,
    UINT  Size
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_INCOMING_DROP_PARTY</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_INCOMING_DROP_PARTY</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



<a href="..\ndis\nf-ndis-ndismcmdispatchincomingdropparty.md">
   NdisMCmDispatchIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingdropparty.md">
   NdisCmDispatchIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndisfreetonpagedlookasidelist.md">
   NdisFreeToNPagedLookasideList</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_INCOMING_DROP_PARTY callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

