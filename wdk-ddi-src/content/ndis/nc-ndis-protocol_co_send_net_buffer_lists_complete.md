---
UID: NC:ndis.PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE
title: PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE
author: windows-driver-content
description: The ProtocolCoSendNetBufferListsComplete function completes a send operation that the protocol driver initiated with a call to the NdisCoSendNetBufferLists function.Note  You must declare the function by using the PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocolcosendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: fb4b00c0-0b14-48dd-a6f2-aae659c6bb28
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocolcosendnetbufferlistscomplete, ProtocolCoSendNetBufferListsComplete callback function [Network Drivers Starting with Windows Vista], ProtocolCoSendNetBufferListsComplete, PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE, PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE, ndis/ProtocolCoSendNetBufferListsComplete, condis_sendrcv_ref_d2516eb4-44f1-4bae-a4f8-5a1ddd069c5a.xml
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
-	ProtocolCoSendNetBufferListsComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE callback


## -description


The 
  <i>ProtocolCoSendNetBufferListsComplete</i> function completes a send operation that the protocol driver
  initiated with a call to the 
  <mshelp:link keywords="netvista.ndiscosendnetbufferlists" tabindex="0"><b>
  NdisCoSendNetBufferLists</b></mshelp:link> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE ProtocolCoSendNetBufferListsComplete;

VOID ProtocolCoSendNetBufferListsComplete(
  _In_ NDIS_HANDLE      ProtocolVcContext,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendCompleteFlags
)
{ ... }
````


## -parameters




#### - ProtocolVcContext [in]

A handle to a protocol driver-allocated context area in which this driver maintains the
     per-virtual connection (VC) run-time state information. A client or stand-alone call manager supplied
     this handle either when it called the 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> function or from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


#### - NetBufferLists [in]

A pointer to a list of 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that the
     protocol driver supplied in a previous call to the 
     <mshelp:link keywords="netvista.ndiscosendnetbufferlists" tabindex="0"><b>
     NdisCoSendNetBufferLists</b></mshelp:link> function.


#### - SendCompleteFlags [in]

NDIS flags that can be combined with a bitwise OR operation. To clear all of the flags, set this
     parameter to zero. 
     <i>ProtocolCoSendNetBufferListsComplete</i> supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag,
     which; if set, indicates that the current IRQL is DISPATCH_LEVEL. For more information about this flag,
     see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


## -returns


None



## -remarks


The 
    <i>ProtocolCoSendNetBufferListsComplete</i> function is required for CoNDIS protocol drivers. 
    <i>ProtocolCoSendNetBufferListsComplete</i> performs whatever postprocessing is necessary to complete a
    send operation. For example, the protocol driver can notify the clients that requested the driver to send
    the network data that the send operation is complete.

NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i> after the underlying miniport driver calls the 
    <mshelp:link keywords="netvista.ndismsendnetbufferlistscomplete" tabindex="0"><b>
    NdisMCoSendNetBufferListsComplete</b></mshelp:link> function. A complete send operation does not necessarily imply
    that an underlying miniport driver has transmitted the specified network data. For example, a miniport
    driver can indicate that a send operation has completed as soon as it transfers the network data to the
    network interface card (NIC) hardware.

When NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i>, the protocol driver regains ownership of all of the
    resources that are associated with the NET_BUFFER_LIST structures that the 
    <i>NetBufferLists</i> parameter specifies.

NDIS always submits protocol driver-supplied network data to the underlying drivers in the
    protocol-determined order that was passed to 
    <b>NdisCoSendNetBufferLists</b>. However, the underlying driver can complete the send requests in any
    order. That is, protocol drivers can rely on NDIS to submit network data in "first in, first out" (FIFO)
    order to the underlying driver. However, protocol drivers cannot rely on the underlying driver to call 
    <b>NdisMCoSendNetBufferListsComplete</b> in the same order.

NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i> at IRQL&lt;= DISPATCH_LEVEL.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>ProtocolCoSendNetBufferListsComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoSendNetBufferListsComplete</i> function that is named "MyCoSendNetBufferListsComplete", use the <b>PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE MyCoSendNetBufferListsComplete;</pre>
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
 MyCoSendNetBufferListsComplete(
    NDIS_HANDLE  ProtocolVcContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  SendCompleteFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<mshelp:link keywords="netvista.ndismcosendnetbufferlistscomplete" tabindex="0"><b>
   NdisMCoSendNetBufferListsComplete</b></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545115">CoNDIS Protocol Driver Send and Receive Functions</a>

<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>

<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">ProtocolCoReceiveNetBufferLists</a>

<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>

<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CO_SEND_NET_BUFFER_LISTS_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

