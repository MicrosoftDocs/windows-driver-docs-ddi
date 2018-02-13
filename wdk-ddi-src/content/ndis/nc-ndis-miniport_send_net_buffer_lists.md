---
UID: NC:ndis.MINIPORT_SEND_NET_BUFFER_LISTS
title: MINIPORT_SEND_NET_BUFFER_LISTS
author: windows-driver-content
description: NDIS calls the MiniportSendNetBufferLists function to transmit network data that is contained in a linked list of NET_BUFFER_LIST structures.
old-location: netvista\miniportsendnetbufferlists.htm
old-project: netvista
ms.assetid: 0bd5966d-66a6-4548-8c84-7cedced2cf40
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportsendnetbufferlists, MiniportSendNetBufferLists callback function [Network Drivers Starting with Windows Vista], MiniportSendNetBufferLists, MINIPORT_SEND_NET_BUFFER_LISTS, MINIPORT_SEND_NET_BUFFER_LISTS, ndis/MiniportSendNetBufferLists, ndis_sendrcv_ref_2af2df46-99cf-4bae-9dea-12358fb0b489.xml
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
req.ddi-compliance: NdisTimedDataHang, NdisTimedDataSend
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
-	MiniportSendNetBufferLists
product: Windows
targetos: Windows
req.typenames: "*LPVIDEO_STREAM_INIT_PARMS, VIDEO_STREAM_INIT_PARMS"
---

# MINIPORT_SEND_NET_BUFFER_LISTS callback


## -description


NDIS calls the 
   <i>MiniportSendNetBufferLists</i> function to transmit network data that is contained in a linked list of 
   <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_SEND_NET_BUFFER_LISTS</b> type. For
   more information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_SEND_NET_BUFFER_LISTS MiniportSendNetBufferLists;

VOID MiniportSendNetBufferLists(
  _In_ NDIS_HANDLE      MiniportAdapterContext,
  _In_ PNET_BUFFER_LIST NetBufferList,
  _In_ NDIS_PORT_NUMBER PortNumber,
  _In_ ULONG            SendFlags
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information about an adapter.


### -param NetBufferList [in]

A pointer to the first 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure in a linked list
     of NET_BUFFER_LIST structures. Each NET_BUFFER_LIST structure in the list describes a list of 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures. Each NET_BUFFER structure
     in the list maps to a chain of MDLs. The MDLs contain the network data.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. To assign a miniport adapter port number,
     call the 
     <a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a> function. A zero
     value identifies the default port of a miniport adapter.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     





#### NDIS_SEND_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.



#### NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

Specifies that NDIS should check for loopback. By default, NDIS does not loop back data to the
       driver that submitted the send request. An overlying driver can override this behavior by setting this
       flag. When this flag is set, NDIS identifies all the NET_BUFFER structures that contain data that
       matches the receive criteria for the binding. NDIS indicates NET_BUFFER structures that match the
       criteria to the overlying driver. This flag has no affect on checking for loopback, or looping back,
       on other bindings.


## -returns



None




## -remarks



<i>MiniportSendNetBufferLists</i> is a required function for miniport drivers. When an overlying driver
    calls the 
    <a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a> function,
    NDIS calls the 
    <i>MiniportSendNetBufferLists</i> function of the bound miniport driver.

When transmitting the network data that NDIS passes in the <i>NetBufferLists</i> parameter, the miniport driver must use the following guidelines:<ol>
<li>
The order of the <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in each <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure must be preserved.

</li>
<li>
The order of the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures should be preserved if they are to be transmitted on the same connection.

</li>
<li>
If the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures are to be transmitted on different connections, they can be split into multiple transmit queues if  the following features are in use. In this case, the order of the <b>NET_BUFFER_LIST</b> structures for each connection should be preserved.

<ul>
<li>
Receive side scaling (RSS) (The RSS hash value in the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure can be used as an index into the RSS indirection table.)

</li>
<li>
Virtual Machine Queue (VMQ) (The queue identifier of the outgoing queue is set in the <b>NetBufferListFilteringInfo</b> OOB information. For more information, see <a href="https://msdn.microsoft.com/a34f0708-e477-4acc-b854-f00f752be423">VMQ Transmit Path</a>.)

</li>
<li>
IEEE 802.1 Data Center Bridging (DCB) (You can key off the Traffic Class (TC).)

</li>
<li>
IEEE 802.1p (You can key off 802.1p tags without DCB.) 

</li>
</ul>
</li>
</ol>


Miniport drivers accept all send requests that NDIS makes by calling the 
    <i>MiniportSendNetBufferLists</i> function. If a miniport driver cannot complete a send request
    immediately, the driver must hold the request in a queue until it can complete the request. While a send
    request is pending, the miniport driver retains ownership of the NET_BUFFER_LIST structures and all the
    protocol-allocated resources associated with the NET_BUFFER_LIST structures.

The miniport driver must call the 
    <a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
    NdisMSendNetBufferListsComplete</a> function to complete the send requests for all NET_BUFFER_LIST
    structures. To improve system performance, the driver can create a linked list that contains the
    NET_BUFFER_LIST structures from multiple send requests. The driver can then pass such a linked list in a
    single call to 
    <b>NdisMSendNetBufferListsComplete</b>.NET_BUFFER_LIST structures and other associated resources should
    be treated as inaccessible by the miniport driver as soon as the driver calls 
    <b>NdisMSendNetBufferListsComplete</b>.

The 
    <i>MiniportSendNetBufferLists</i> function must synchronize access to its internal queues of network data
    with the driver's other 
    <i>MiniportXxx</i> functions that access the same queues. A miniport driver can use spin locks to
    synchronize access to the queues.

Protocol drivers are responsible for determining what network data is required, based on the medium
    type that the bound miniport driver selected. However, a protocol driver can supply network data that
    specifies packets that are shorter than the minimum packet size for the selected medium. In this case, 
    <i>MiniportSendNetBufferLists</i> must pad the packets with zeros if the selected medium imposes a
    minimum-length requirement on the transmit packet size.

If the miniport driver set the NDIS_MAC_OPTION_NO_LOOPBACK flag when NDIS queried the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a> OID, the miniport
    driver must not attempt to loop back any network data. NDIS provides software loopback support for such a
    driver.

NDIS calls 
    <i>MiniportSendNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportSendNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportSendNetBufferLists</i> function that is named "MySendNetBufferLists", use the <b>MINIPORT_SEND_NET_BUFFER_LISTS</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_SEND_NET_BUFFER_LISTS MySendNetBufferLists;</pre>
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
 MySendNetBufferLists(
    NDIS_HANDLE  MiniportAdapterContext,
    PNET_BUFFER_LIST  NetBufferList,
    NDIS_PORT_NUMBER  PortNumber,
    ULONG  SendFlags
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_SEND_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_SEND_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nf-ndis-ndismallocateport.md">NdisMAllocatePort</a>



<a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
   NdisMSendNetBufferListsComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_SEND_NET_BUFFER_LISTS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

