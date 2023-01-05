---
UID: NF:ndis.NdisAllocateBufferPool
tech.root: netvista
title: NdisAllocateBufferPool
ms.date: 01/04/2023
targetos: Windows
description: This function returns a handle with which the caller can allocate buffer descriptors by calling NdisAllocateBuffer.
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
 - NdisAllocateBufferPool
f1_keywords:
 - NdisAllocateBufferPool
 - ndis/NdisAllocateBufferPool
dev_langs:
 - c++
helpviewer_keywords:
 - NdisAllocateBufferPool
---

# NdisAllocateBufferPool

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

This function returns a handle with which the caller can allocate buffer descriptors by calling the [NdisAllocateBuffer](nf-ndis-ndisallocatebuffer.md) function.

## -parameters

### -param Status [out]

Pointer to a caller-supplied variable in which this function returns the final status of the buffer pool allocation.

### -param PoolHandle [out]

Pointer to a caller-supplied variable in which this function returns a handle to the buffer pool. This handle is a required parameter to the NDIS buffer functions that the driver calls subsequently.

### -param NumberOfDescriptors [in]

Specifies the number of buffer descriptors that the caller expects to allocate from the buffer pool without releasing any allocated buffer descriptors back to the pool.

## -remarks

Always returns NDIS\_STATUS\_SUCCESS.

After this function returns, the driver calls the **NdisAllocateBuffer** function one or more times to allocate the buffer descriptors that it requires. A driver should call this function during initialization.

The *NumberOfDescriptors* parameter specified by an NIC driver usually depends on the features of the NIC. For example, the driver of a bus master DMA NIC with ring buffers would specify at least a large enough *NumberOfDescriptors* to map the full ring.

The *NumberOfDescriptors* specified in the call to this function is the effective limit on how many times the driver can call **NdisAllocateBuffer** before it must call the [NdisFreeBuffer](https://msdn.microsoft.com/library/ff551981\(v=vs.85\)) function to return a buffer descriptor to the free list for the buffer pool.

When a driver no longer needs the buffer pool that it allocated, it calls the [NdisFreeBufferPool]\(/previous-versions/windows/hardware/network/ff551984(v=vs.85)) function to release the buffer pool handle.

The driver must release any spin lock that it is holding before calling this function.

All lower-level NDIS drivers must allocate all buffer descriptors that they chain to packets from a buffer pool. Only highest-level protocol drivers can be given OS-dependent descriptors mapping virtual memory ranges. If these memory descriptors are equivalent to NDIS buffer descriptors, a highest-level protocol can pass such descriptors as parameters to NDIS functions.

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [NdisAdjustBufferLength]\(/previous-versions/windows/hardware/network/ff550733(v=vs.85))
- [NdisAllocateBuffer](nf-ndis-ndisallocatebuffer.md)
- [NdisChainBufferAtBack]\(/previous-versions/windows/hardware/network/ff550830(v=vs.85))
- [NdisChainBufferAtFront]\(/previous-versions/windows/hardware/network/ff550837(v=vs.85))
- [NdisFreeBuffer]\(/previous-versions/windows/hardware/network/ff551981(v=vs.85))
- [NdisFreeBufferPool]\(/previous-versions/windows/hardware/network/ff551984(v=vs.85))
- [NdisQueryBuffer](https://msdn.microsoft.com/library/aa520905\(v=msdn.10\))
- [NdisReleaseSpinLock](https://msdn.microsoft.com/library/aa520935\(v=msdn.10\))
