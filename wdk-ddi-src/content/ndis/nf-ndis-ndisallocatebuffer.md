---
UID: NF:ndis.NdisAllocateBuffer
tech.root: 
title: NdisAllocateBuffer
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
 - NdisAllocateBuffer
f1_keywords:
 - NdisAllocateBuffer
 - ndis/NdisAllocateBuffer
dev_langs:
 - c++
helpviewer_keywords:
 - NdisAllocateBuffer
---

# NdisAllocateBuffer function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisAllocateBuffer** creates a buffer descriptor mapping a specified virtual (sub)range within an already allocated, nonpaged memory block.

## -parameters

### -param Status [out]  

Pointer to a caller-supplied variable in which this function returns the final status of the buffer allocation, which is NDIS\_STATUS\_SUCCESS if it returned a valid buffer descriptor pointer at *Buffer* and otherwise NDIS\_STATUS\_FAILURE.

### -param Buffer [out]  

Pointer to a caller-supplied variable in which this function returns a pointer to the allocated buffer descriptor.

### -param PoolHandle [in, optional]

Specifies the handle returned by a preceding call to [NdisAllocateBufferPool](nf-ndis-ndisallocatebufferpool.md).

### -param VirtualAddress [in]  

Pointer to the base virtual address of previously allocated system-space memory to be mapped in the returned buffer descriptor.

### -param Length [in]  

Specifies the number of bytes to be mapped.

## -remarks

Return value: None

**NdisAllocateBuffer** allocates storage for and initializes a buffer descriptor to map a specified range of previously allocated memory, such as memory used for a packet header or a NIC receive buffer.

Buffer descriptor allocation draws on the buffer pool that [NdisAllocateBufferPool](nf-ndis-ndisallocatebufferpool.md) creates. A driver can call **NdisAllocateBuffer** as many times as necessary to allocate the buffer descriptors that it requires if it called **NdisAllocateBufferPool** during initialization.

All lower-level NDIS drivers must allocate all buffer descriptors that they chain to packets from buffer pool. Only highest-level protocol drivers can be given OS-dependent descriptors mapping virtual memory ranges, and, if these memory descriptors are equivalent to NDIS buffer descriptors, a highest-level protocol can pass such descriptors as parameters to *NdisXxx* functions.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Target platform</p></td>
<td><a href="https://go.microsoft.com/fwlink/p/?linkid=531356">Universal</a></td>
</tr>
<tr class="even">
<td><p>Version</p></td>
<td><p>Not supported for NDIS 6.0 drivers in Windows Vista. Use NdisAllocateMdl instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Ndis.h (include Ndis.h)</td>
</tr>
<tr class="even">
<td><p>Library</p></td>
<td>Ndis.lib</td>
</tr>
<tr class="odd">
<td><p>IRQL</p></td>
<td><p>&lt;= DISPATCH_LEVEL.</p></td>
</tr>
</tbody>
</table>

## -see-also

- [**NdisAllocateBufferPool**](ff550741\(v=vs.85\).md)
- [**NdisAllocateMemoryWithTag**](ff550767\(v=vs.85\).md)
- [**NdisFreeBuffer**](ff551981\(v=vs.85\).md)
