---
UID: NF:ndis.NdisAllocatePacketPoolEx
tech.root: netvista
title: NdisAllocatePacketPoolEx
ms.date: 01/04/2023
targetos: Windows
description: This function allocates and initializes a block of storage for a pool of packet descriptors.
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
req.lib: Ndis.lib
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
 - NdisAllocatePacketPoolEx
f1_keywords:
 - NdisAllocatePacketPoolEx
 - ndis/NdisAllocatePacketPoolEx
dev_langs:
 - c++
helpviewer_keywords:
 - NdisAllocatePacketPoolEx
---

# NdisAllocatePacketPoolEx (Windows CE 5.0)

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

This function allocates and initializes a block of storage for a pool of packet descriptors.

## -parameters

### -param Status [out]

Points to a caller-supplied variable in which this function returns the status of the packet pool allocation.

### -param PoolHandle [out]

Points to a caller-supplied variable in which this function returns a handle to the packet pool. This handle is a required parameter to the **Ndis*XXX*Packet** functions that the driver calls subsequently.

### -param NumberOfDescriptors [in]

Specifies the number of packet descriptors that the pool should contain for anticipated normal use. The maximum *NumberOfDescriptors* that can be allocated is 0xFFFF. If an attempt is made to allocate more than this, **NdisAllocatePacketPoolEx** returns a *Status* of NDIS\_STATUS\_RESOURCES.

### -param NumberOfOverflowDescriptors [in]

Specifies the number of packet descriptors reserved for an overflow situation, that is, when all the descriptors specified by *NumberOfDescriptors* are in use. If the sum of this parameter and *NumberOfDescriptors* exceeds 0xFFFF, **NdisAllocatePacketPoolEx** reduces the value supplied as this parameter so that the total *NumberOfDescriptors* and *NumberOfOverflowDescriptors* equals 0xFFFF.

### -param ProtocolReservedLength [in]

Specifies the number of bytes to be allocated for the **ProtocolReserved** array of each packet descriptor. For packet descriptors to be used in receive indications, this parameter is 4\*size of (PVOID).

## -remarks

The following table shows the possible return values for this function.

<table>
<thead>
<tr class="header">
<th>Status</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>NDIS_STATUS_SUCCESS</td>
<td>The driver can make calls to <a href="aa447907(v=msdn.10).md">NdisAllocatePacket</a> when it needs packet descriptors to make indications up to higher-level drivers or to send packets down to lower-level drivers.</td>
</tr>
<tr class="even">
<td>NDIS_STATUS_RESOURCES</td>
<td>The attempt to allocate packet pool failed, possibly due to a shortage of memory. This return does not necessarily mean that a subsequent call will fail. However, the caller might attempt to decrease the <em>NumberOfDescriptors</em> and call again immediately.</td>
</tr>
</tbody>
</table>

A successful call to **NdisAllocatePacketPoolEx** returns a handle to the packet pool, which the caller should save. Usually, the driver next calls **NdisAllocatePacket** one or more times with this handle to allocate a set of packet descriptors.

**NdisAllocatePacketPoolEx** statically allocates only enough memory to accommodate the number of packet descriptors specified by *NumberOfDescriptors*. The total number of packet descriptors that can be allocated from the pool with calls to **NdisAllocatePacket** is the lesser of 0xFFFF or the sum of *NumberOfDescriptors* and *NumberOfOverflowDescriptors* originally passed to **NdisAllocatePacketPoolEx**. Overflow descriptors are allocated dynamically only during an overflow situation — that is, when the given *NumberOfDescriptors* have already been allocated and are still in use.

The sum of *NumberOfDescriptors* and *NumberOfOverflowDescriptors* is the effective limit on how many times the driver can call **NdisAllocatePacket** before it must call [NdisFreePacket](aa447955\(v=msdn.10\).md) to return a packet descriptor to the free list for the packet pool. When no overflow descriptor has yet been allocated, **NdisFreePacket** returns the packet descriptor to the statically allocated pool. If one or more overflow descriptors have already been allocated, **NdisFreePacket** returns the packet descriptor to system memory — not to the pool.

The caller of **NdisAllocatePacketPoolEx** should set *NumberOfDescriptors* to the number of packet descriptors needed for anticipated normal loads. The driver should set *NumberOfOverflowDescriptors* to the number of additional descriptors needed to accommodate anticipated peak loads. If the total possible number of packet descriptors (*NumberOfDescriptors* plus *NumberOfOverflowDescriptors*) has been allocated from the pool, a call to **NdisAllocatePacket** returns NDIS\_STATUS\_RESOURCES.

As packets sent or indicated are returned to the allocating driver, it can reuse each packet descriptor after calling [NdisReinitializePacket](ms904135\(v=msdn.10\).md) and setting it up again with a chain of buffer descriptors, or the driver can call **NdisFreePacket** to return that packet to the free list. Reinitializing and reusing packets allocated from packet pool is far faster than freeing and, then, having to reallocate them again. Before a driver calls **NdisReinitializePacket** with a packet descriptor, it must save the pointers to buffer descriptors that are chained to the packet descriptor, because **NdisReinitializePacket** sets the head of the buffer chain to NULL.

When a driver no longer needs packet descriptors, it calls [(nf-ndis-ndisfreepacketpool.md) to release the storage that it allocated with **NdisAllocatePacketPoolEx**.

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [NdisAllocatePacket](aa447907\(v=msdn.10\).md)
- [NdisDprAllocatePacket](aa447938\(v=msdn.10\).md)
- [NdisDprAllocatePacketNonInterlocked](aa447939\(v=msdn.10\).md)
- [NdisFreePacketPool](aa447956\(v=msdn.10\).md)
- [NdisMIndicateReceivePacket](aa448038\(v=msdn.10\).md)
- [NDIS\_PACKET](ms904084\(v=msdn.10\).md)
- [NDIS\_PACKET\_OOB\_DATA](ms904087\(v=msdn.10\).md)
- [NdisReinitializePacket](ms904135\(v=msdn.10\).md)
- [NdisSendPackets](ms904962\(v=msdn.10\).md)
- [NdisUnchainBufferAtBack](ms905036\(v=msdn.10\).md)
- [NdisUnchainBufferAtFront](ms905037\(v=msdn.10\).md)
