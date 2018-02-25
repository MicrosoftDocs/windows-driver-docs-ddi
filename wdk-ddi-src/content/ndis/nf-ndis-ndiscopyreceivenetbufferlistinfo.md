---
UID: NF:ndis.NdisCopyReceiveNetBufferListInfo
title: NdisCopyReceiveNetBufferListInfo function
author: windows-driver-content
description: Intermediate drivers call the NdisCopyReceiveNetBufferListInfo function to copy the NET_BUFFER_LIST information in a received NET_BUFFER_LIST structure.
old-location: netvista\ndiscopyreceivenetbufferlistinfo.htm
old-project: netvista
ms.assetid: 94dc33f4-06ad-4b36-9150-6fb7d491a247
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, C, I, L, N, NdisCopyReceiveNetBufferListInfo, NdisCopyReceiveNetBufferListInfo function [Network Drivers Starting with Windows Vista], R, c, d, e, f, i, n, ndis/NdisCopyReceiveNetBufferListInfo, ndis_netbuf_functions_ref_c7980afc-64b0-4dc4-812e-1a89254df50a.xml, netvista.ndiscopyreceivenetbufferlistinfo, o, p, r, s, t, u, v, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCopyReceiveNetBufferListInfo
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCopyReceiveNetBufferListInfo function


## -description


Intermediate drivers call the 
  <b>NdisCopyReceiveNetBufferListInfo</b> function to copy the 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> information in a received
  <b>NET_BUFFER_LIST</b> structure.


## -syntax


````
VOID NdisCopyReceiveNetBufferListInfo(
  _In_ PNET_BUFFER_LIST DestNetBufferList,
  _In_ PNET_BUFFER_LIST SrcNetBufferList
);
````


## -parameters




### -param DestNetBufferList [in]

A pointer to the destination <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


### -param SrcNetBufferList [in]

A pointer to the source <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -returns



None




## -remarks



When an intermediate driver or filter driver gets receive indications from an underlying driver, it
    can, for example, clone the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure or allocate a new
    structure to propagate the request to overlying drivers. The driver should use 
    <b>NdisCopyReceiveNetBufferListInfo</b> to copy the <b>NET_BUFFER_LIST</b> information, including private NDIS
    information, to the new structure.

To copy the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> information on the send path, use the 
    <a href="..\ndis\nf-ndis-ndiscopysendnetbufferlistinfo.md">
    NdisCopySendNetBufferListInfo</a> function.

The following <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> items are copied in a call to <b>NdisCopyReceiveNetBufferListInfo</b>:

<table>
<tr>
<th>Copied Item</th>
<th>Starting Windows Version</th>
</tr>
<tr>
<td>TcpIpChecksumNetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>IPsecOffloadV1NetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>TcpReceiveNoPush</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>Ieee8021QNetBufferListInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>MediaSpecificInformation</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListFrameType</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListHashValue</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListHashInfo</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>IPsecOffloadV2TunnelNetBufferListInfo</td>
<td>Windows Vista with Service Pack 1 (SP1)</td>
</tr>
<tr>
<td>IPsecOffloadV2HeaderNetBufferListInfo</td>
<td>Windows Vista with SP1</td>
</tr>
<tr>
<td>VirtualSubnetInfo</td>
<td>Windows 8 (AMD64 only)</td>
</tr>
<tr>
<td>NetBufferListFilteringInfo</td>
<td>Windows 8</td>
</tr>
</table>
 




## -see-also

<a href="..\ndis\nf-ndis-ndiscopysendnetbufferlistinfo.md">
    NdisCopySendNetBufferListInfo</a>



<a href="https://msdn.microsoft.com/f7f19e48-cb63-458d-b175-6f99080e4cdf">NET_BUFFER_LIST Structure</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCopyReceiveNetBufferListInfo function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

