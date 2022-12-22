---
UID: NF:ndis.NdisFreePacketPool
tech.root: 
title: NdisFreePacketPool
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisFreePacketPool
f1_keywords:
 - NdisFreePacketPool
 - ndis/NdisFreePacketPool
dev_langs:
 - c++
helpviewer_keywords:
 - NdisFreePacketPool
---

# NdisFreePacketPool

## -description

This function releases a handle to a block of packet pool that was allocated with the **NdisAllocatePacketPool** function.

## -parameters

### -param PoolHandle

Handle returned when the driver called **NdisAllocatePacketPool**. The pool handle is no longer valid after this function returns.

## -remarks

This function frees the storage for the packet pool. Before calling this function, the driver must call the **NdisFreePacket** function as many times as necessary to release all packet descriptors that it has allocated with the **NdisAllocatePacket** function, but not yet freed.

The driver must also release any spin lock that it is holding before calling this function.

A driver that calls this function runs at IRQL \<= DISPATCH\_LEVEL.

<table>
<thead>
<tr class="header">
<th>Runs on</th>
<th>Versions</th>
<th>Defined in</th>
<th>Include</th>
<th>Link to</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Windows CE OS</td>
<td>2.0 and later</td>
<td>Ndis.h</td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>

> **Note**   This API is part of the complete Windows CE OS package as provided by Microsoft. The functionality of a particular platform is determined by the original equipment manufacturer (OEM) and some devices may not support this API.

## -see-also

- [NdisAllocatePacket](ms892685\(v=msdn.10\).md)
- [NdisAllocatePacketPool](ms892686\(v=msdn.10\).md)
- [NdisFreePacket](ms892703\(v=msdn.10\).md)
- [NdisReleaseSpinLock](ms892867\(v=msdn.10\).md)
