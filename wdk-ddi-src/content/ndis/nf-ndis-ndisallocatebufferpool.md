---
UID: NF:ndis.NdisAllocateBufferPool
tech.root: 
title: NdisAllocateBufferPool
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

When a driver no longer needs the buffer pool that it allocated, it calls the [NdisFreeBufferPool](ms921060\(v=msdn.10\).md) function to release the buffer pool handle.

The driver must release any spin lock that it is holding before calling this function.

All lower-level NDIS drivers must allocate all buffer descriptors that they chain to packets from a buffer pool. Only highest-level protocol drivers can be given OS-dependent descriptors mapping virtual memory ranges. If these memory descriptors are equivalent to NDIS buffer descriptors, a highest-level protocol can pass such descriptors as parameters to NDIS functions.

**OS Versions:** Windows CE .NET 4.0 and later.  

## -see-also

- [NdisAdjustBufferLength](ms920735\(v=msdn.10\).md)
- [NdisAllocateBuffer](nf-ndis-ndisallocatebuffer.md)
- [NdisChainBufferAtBack](ms920842\(v=msdn.10\).md)
- [NdisChainBufferAtFront](ms920912\(v=msdn.10\).md)
- [NdisFreeBuffer](ms921059\(v=msdn.10\).md)
- [NdisFreeBufferPool](ms921060\(v=msdn.10\).md)
- [NdisQueryBuffer](https://msdn.microsoft.com/library/aa520905\(v=msdn.10\))
- [NdisReleaseSpinLock](https://msdn.microsoft.com/library/aa520935\(v=msdn.10\))
