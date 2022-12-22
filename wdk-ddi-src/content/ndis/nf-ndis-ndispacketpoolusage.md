---
UID: NF:ndis.NdisPacketPoolUsage
tech.root: 
title: NdisPacketPoolUsage
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
 - NdisPacketPoolUsage
f1_keywords:
 - NdisPacketPoolUsage
 - ndis/NdisPacketPoolUsage
dev_langs:
 - c++
helpviewer_keywords:
 - NdisPacketPoolUsage
---

# NdisPacketPoolUsage (Windows CE 5.0)

## -description

This function returns the number of packet descriptors currently allocated from a packet pool.

## -parameters

### -param PoolHandle [in]

Specifies a handle returned by [NdisAllocatePacketPool](aa447908\(v=msdn.10\).md) or [NdisAllocatePacketPoolEx](aa447909\(v=msdn.10\).md).

## -returns

Returns the number of packet descriptors currently allocated from the given packet pool.

## -remarks

Before allocating packet descriptors for a send or receive indication, an NDIS driver can call **NdisPacketPoolUsage** to determine whether it has enough spare packet descriptors available for the send/receive, particularly if the driver has allocated more than one packet pool.

An NDIS driver also can call this function to be sure that all descriptors have been returned to the given packet pool before it calls [NdisFreePacketPool](aa447956\(v=msdn.10\).md).

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [NdisAllocatePacket](aa447907\(v=msdn.10\).md)
- [NdisAllocatePacketPool](aa447908\(v=msdn.10\).md)
- [NdisAllocatePacketPoolEx](aa447909\(v=msdn.10\).md)
- [NdisDprAllocatePacket](aa447938\(v=msdn.10\).md)
- [NdisDprAllocatePacketNonInterlocked](aa447939\(v=msdn.10\).md)
- [NdisFreePacketPool](aa447956\(v=msdn.10\).md)
- [NdisPacketSize](aa448321\(v=msdn.10\).md)
