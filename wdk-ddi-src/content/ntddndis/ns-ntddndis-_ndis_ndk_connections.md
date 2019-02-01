---
UID: NS:ntddndis._NDIS_NDK_CONNECTIONS
title: _NDIS_NDK_CONNECTIONS (ntddndis.h)
description: The NDIS_NDK_CONNECTIONS structure describes the NDK connections that are active on a miniport adapter.
old-location: netvista\ndis_ndk_connections.htm
tech.root: netvista
ms.assetid: 24149E73-6BA8-4C5E-8649-25A90A3D01AF
ms.date: 05/02/2018
ms.keywords: NDIS_NDK_CONNECTIONS, NDIS_NDK_CONNECTIONS structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_CONNECTIONS, PNDIS_NDK_CONNECTIONS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_CONNECTIONS, netvista.ndis_ndk_connections, ntddndis/NDIS_NDK_CONNECTIONS, ntddndis/PNDIS_NDK_CONNECTIONS
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_NDK_CONNECTIONS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NDK_CONNECTIONS
---

# _NDIS_NDK_CONNECTIONS structure


## -description


The <b>NDIS_NDK_CONNECTIONS</b> structure describes the NDK connections that are active on a miniport adapter.


## -struct-fields




### -field Header

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_NDK_CONNECTIONS</b> structure. Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_NDK_CONNECTIONS_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to (USHORT)min(MAXUSHORT, NDIS_SIZEOF_NDK_CONNECTIONS_REVISION_1(n)).</li>
</ul>

### -field Flags

 


### -field Count

The number of elements in the connection array that is passed in the <b>Connections</b> member. Each element in the array is an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451562">NDIS_NDK_CONNECTION_ENTRY</a> structure. 


### -field NDConnectionsMappedtoTCPConnections

A BOOLEAN value that specifies how the connections are mapped. If the RDMA technology for the NDK provider requires the provider to map ND connections to TCP connections, the NDK provider must set the <b>NDConnectionsMappedtoTCPConnections</b> member to TRUE. Otherwise, <b>NDConnectionsMappedtoTCPConnections</b> is FALSE.


### -field Connections

A variable-sized array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451562">NDIS_NDK_CONNECTION_ENTRY</a> structures where the size of the array is determined by the number of connections being returned. The <b>Count</b> member  specifies the number of elements in the connection array. 


## -remarks



The <b>NDIS_NDK_CONNECTIONS</b> structure is returned with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451810">OID_NDK_CONNECTIONS</a> OID. The <b>InformationBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure contains a pointer to this structure.



This structure is variable-sized and contains elements equal in number to the number of connections that are returned. The actual size of the connection array as an element count is indicated by the <b>Count</b> member. 

If the RDMA technology for the NDK provider requires the provider to map ND connections to TCP connections, the NDK provider must also report the underlying TCP connection 4-tuple for each ND connection as follows:

<ul>
<li>Set the <b>NDConnectionsMappedtoTCPConnections</b> member to TRUE.</li>
<li>Use two consecutive entries for each ND connection. The first entry contains the ND addressing information (local and remote IP address, and ND port number) and the immediate next entry contains the corresponding TCP connection's addressing information (local and remote IP address, and TCP port number). 

</li>
<li>Members other than addressing information (For example, <b>UserModeOwner</b> and <b>OwnerPid</b>) must be set only in the first entry  and left untouched in the next entry. Therefore, entries at index 0, 2, 4, and so on, contain ND addressing information (plus properly filled-in other members) and entries at index 1, 3, 5 and so on, contain TCP addressing info (where other members are left untouched).

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451562">NDIS_NDK_CONNECTION_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451810">OID_NDK_CONNECTIONS</a>
 

 

