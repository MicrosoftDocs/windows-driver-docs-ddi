---
UID: NF:ndis.NdisCopySendNetBufferListInfo
title: NdisCopySendNetBufferListInfo function
author: windows-driver-content
description: Intermediate drivers call the NdisCopySendNetBufferListInfo function to copy the NET_BUFFER_LIST information in a transmit NET_BUFFER_LIST structure.
old-location: netvista\ndiscopysendnetbufferlistinfo.htm
old-project: netvista
ms.assetid: 9c8227ea-53e4-47c9-ab74-84e42b0cbbe5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisCopySendNetBufferListInfo, netvista.ndiscopysendnetbufferlistinfo, NdisCopySendNetBufferListInfo function [Network Drivers Starting with Windows Vista], ndis/NdisCopySendNetBufferListInfo, ndis_netbuf_functions_ref_6bea2e25-d488-4bf2-879b-1ace04c66b68.xml
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
-	NdisCopySendNetBufferListInfo
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCopySendNetBufferListInfo function


## -description


Intermediate drivers call the 
  <b>NdisCopySendNetBufferListInfo</b> function to copy the 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> information in a transmit
  <b>NET_BUFFER_LIST</b> structure.


## -syntax


````
VOID NdisCopySendNetBufferListInfo(
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


When an intermediate driver or filter driver receives a transmit request from an overlying driver, it
    can, for example, clone the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure or allocate a new
    structure to propagate the request to underlying drivers. The driver should use 
    <b>NdisCopySendNetBufferListInfo</b> to copy the <b>NET_BUFFER_LIST</b> information, including private NDIS
    information, to the new structure.

To copy the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> information on the receive path, use the 
    <mshelp:link keywords="netvista.ndiscopyreceivenetbufferlistinfo" tabindex="0"><b>
    NdisCopyReceiveNetBufferListInfo</b></mshelp:link> function.

The following <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> items are copied in a call to <b>NdisCopySendNetBufferListInfo</b>:
<table>
<tr>
<th>Copied Item </th>
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
<td>TcpLargeSendNetBufferListInfo</td>
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
<td>NetBufferListCancelId</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>NetBufferListProtocolId</td>
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

<mshelp:link keywords="netvista.ndiscopyreceivenetbufferlistinfo" tabindex="0"><b>
   NdisCopyReceiveNetBufferListInfo</b></mshelp:link>

<a href="https://msdn.microsoft.com/f7f19e48-cb63-458d-b175-6f99080e4cdf">NET_BUFFER_LIST Structure</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCopySendNetBufferListInfo function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

