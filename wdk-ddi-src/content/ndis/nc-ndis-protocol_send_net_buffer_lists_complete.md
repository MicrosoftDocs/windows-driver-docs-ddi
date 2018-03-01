---
UID: NC:ndis.PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE
title: PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE
author: windows-driver-content
description: The ProtocolSendNetBufferListsComplete function completes a send operation that the protocol driver initiated with a call to the NdisSendNetBufferLists function.Note  You must declare the function by using the PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocolsendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: bc9197c5-ce0b-42b2-8225-fb9d83427ac8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE, ProtocolSendNetBufferListsComplete, ProtocolSendNetBufferListsComplete callback function [Network Drivers Starting with Windows Vista], ndis/ProtocolSendNetBufferListsComplete, ndis_sendrcv_ref_1e393909-0442-45d4-ae57-7ec0f51671a4.xml, netvista.protocolsendnetbufferlistscomplete
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolSendNetBufferListsComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE callback


## -description


The 
  <i>ProtocolSendNetBufferListsComplete</i> function completes a send operation that the protocol driver
  initiated with a call to the 
  <a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">
  NdisSendNetBufferLists</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE ProtocolSendNetBufferListsComplete;

VOID ProtocolSendNetBufferListsComplete(
  _In_ NDIS_HANDLE      ProtocolBindingContext,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendCompleteFlags
)
{ ... }
````


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area that the protocol driver allocated to maintain state information about
     a binding. This handle was passed to NDIS in a previous call to 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>.


### -param NetBufferList


### -param SendCompleteFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag which; if set, indicates
     that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


#### - NetBufferLists [in]

A pointer to a list of 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that the
     protocol driver supplied in a previous call to 
     <a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a>.


## -returns



None




## -remarks



<i>ProtocolSendNetBufferListsComplete</i> is a required function for protocol drivers. 
    <i>ProtocolSendNetBufferListsComplete</i> performs whatever postprocessing is necessary to complete a send
    operation. For example, the protocol driver can notify the clients that requested the protocol to send
    the network data that the send operation is complete.

NDIS calls 
    <i>ProtocolSendNetBufferListsComplete</i> after the underlying miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
    NdisMSendNetBufferListsComplete</a> function. Completion of a send operation usually implies that the
    underlying miniport driver has transmitted the specified network data. However, a miniport driver can
    indicate that a send operation has completed as soon as it transfers the network data to its NIC.

When NDIS calls 
    <i>ProtocolSendNetBufferListsComplete</i>, the protocol driver regains ownership of all of the resources
    associated with the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that are
    specified by the 
    <i>NetBufferLists</i> parameter.

NDIS always submits protocol-supplied network data to the underlying miniport driver in the
    protocol-determined order as passed to 
    <b>NdisSendNetBufferLists</b>. However, the underlying driver can complete the send requests in any
    order. That is, protocol drivers can rely on NDIS to submit network data in FIFO order to the underlying
    driver. However, protocol drivers cannot rely on the underlying driver to call 
    <b>NdisMSendNetBufferListsComplete</b> in the same order.

NDIS calls 
    <i>ProtocolSendNetBufferListsComplete</i> at IRQL&lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolSendNetBufferListsComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolSendNetBufferListsComplete</i> function that is named "MySendNetBufferListsComplete", use the <b>PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE MySendNetBufferListsComplete;</pre>
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
 MySendNetBufferListsComplete(
    NDIS_HANDLE  ProtocolBindingContext,
    PNET_BUFFER_LIST  NetBufferLists,
    ULONG  SendCompleteFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
   NdisMSendNetBufferListsComplete</a>



<a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_SEND_NET_BUFFER_LISTS_COMPLETE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

