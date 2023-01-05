---
UID: NF:ndis.NdisPacketPoolUsage
tech.root: netvista
title: NdisPacketPoolUsage
ms.date: 01/04/2023
targetos: Windows
description: This function returns the number of packet descriptors currently allocated from a packet pool.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: 
req.irql: IRQL <= DISPATCH_LEVEL
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

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

This function returns the number of packet descriptors currently allocated from a packet pool.

## -parameters

### -param PoolHandle [in]

Specifies a handle returned by [NdisAllocatePacketPool]\(/previous-versions/windows/embedded/aa447908(v=msdn.10)) or [NdisAllocatePacketPoolEx](nf-ndis-ndisallocatepacketpoolex.md).

## -returns

Returns the number of packet descriptors currently allocated from the given packet pool.

## -remarks

Before allocating packet descriptors for a send or receive indication, an NDIS driver can call **NdisPacketPoolUsage** to determine whether it has enough spare packet descriptors available for the send/receive, particularly if the driver has allocated more than one packet pool.

An NDIS driver also can call this function to be sure that all descriptors have been returned to the given packet pool before it calls [NdisFreePacketPool](nf-ndis-ndisfreepacketpool.md).

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [NdisAllocatePacket]\(/previous-versions/windows/hardware/network/ff550774(v=vs.85))
- [NdisAllocatePacketPool]\(/previous-versions/windows/embedded/aa447908(v=msdn.10))
- [NdisAllocatePacketPoolEx](nf-ndis-ndisallocatepacketpoolex.md)
- [NdisDprAllocatePacket]\(/previous-versions/windows/hardware/network/ff551932(v=vs.85))
- [NdisDprAllocatePacketNonInterlocked]\(/previous-versions/windows/hardware/network/ff551937(v=vs.85))
- [NdisFreePacketPool](nf-ndis-ndisfreepacketpool.md)
- [NdisPacketSize]\(/previous-versions/windows/embedded/aa448321(v=msdn.10))
