---
UID: NF:ndis.NdisGetNetBufferListProtocolId
title: NdisGetNetBufferListProtocolId function
author: windows-driver-content
description: The NdisGetNetBufferListProtocolId function retrieves the protocol identifier from the NetBufferListInfo member of a NET_BUFFER_LIST structure.
old-location: netvista\ndisgetnetbufferlistprotocolid.htm
old-project: netvista
ms.assetid: a90b1318-ce21-4483-b253-767674fe0a2f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetNetBufferListProtocolId, NdisGetNetBufferListProtocolId function [Network Drivers Starting with Windows Vista], ndis/NdisGetNetBufferListProtocolId, ndis_netbuf_functions_ref_7ce217e7-6d68-4e22-af32-bc984c1b7677.xml, netvista.ndisgetnetbufferlistprotocolid
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetNetBufferListProtocolId
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetNetBufferListProtocolId function


## -description


The 
  <b>NdisGetNetBufferListProtocolId</b> function retrieves the protocol identifier from the 
  <b>NetBufferListInfo</b> member of a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -parameters




### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -returns



<b>NdisGetNetBufferListProtocolId</b> returns a protocol identifier as one of the following
     values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_DEFAULT</b></dt>
</dl>
</td>
<td width="60%">
A default protocol driver identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_TCP_IP</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP protocol identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_IPX</b></dt>
</dl>
</td>
<td width="60%">
The IPX protocol identifier.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_PROTOCOL_ID_NBF</b></dt>
</dl>
</td>
<td width="60%">
The NetBEUI protocol identifier.

</td>
</tr>
</table>
 




## -remarks



NDIS drivers can call the 
    <b>NdisGetNetBufferListProtocolId</b> function to determine the type of protocol driver that created a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. For example,
    miniport drivers that support TCP chimney offload can verify that a NET_BUFFER_LIST structure comes from
    a TCP protocol.

Protocol drivers that create NET_BUFFER_LIST structures should set the protocol identifier by calling
    the 
    <a href="https://msdn.microsoft.com/e143c914-cfb0-4c06-9da7-a2f5ef09afe2">
    NdisSetNetBufferListProtocolId</a> macro or by associating an identifier with a NET_BUFFER_LIST
    pool.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/e143c914-cfb0-4c06-9da7-a2f5ef09afe2">
   NdisSetNetBufferListProtocolId</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetNetBufferListProtocolId function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

