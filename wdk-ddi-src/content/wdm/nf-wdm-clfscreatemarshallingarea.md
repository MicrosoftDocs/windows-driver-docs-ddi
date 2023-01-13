---
UID: NF:wdm.ClfsCreateMarshallingArea
title: ClfsCreateMarshallingArea function (wdm.h)
description: The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["ClfsCreateMarshallingArea function"]
ms.keywords: ClfsCreateMarshallingArea, ClfsCreateMarshallingArea routine [Kernel-Mode Driver Architecture], Clfs_7b5e3208-8dfb-4fbf-b2a9-77ecc5765df6.xml, kernel.clfscreatemarshallingarea, wdm/ClfsCreateMarshallingArea
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsCreateMarshallingArea
 - wdm/ClfsCreateMarshallingArea
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsCreateMarshallingArea
---

## -description

The **ClfsCreateMarshallingArea** routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area.

## -parameters

### -param plfoLog [in]

A pointer to a [**LOG_FILE_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object) structure that represents a CLFS stream. The caller previously obtained this pointer by calling [ClfsCreateLogFile](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile).

### -param ePoolType [in]

A [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type) value that specifies the type of memory (paged, non-paged, for example) that the new marshalling area will use for its log I/O blocks.

### -param pfnAllocBuffer [in, optional]

Either **NULL** or a pointer to a caller-supplied function that allocates a log I/O block for the marshalling area. The allocation function has the following prototype:

```cpp
PVOID
(*PALLOCATE_FUNCTION) (
    IN POOL_TYPE PoolType,
    IN SIZE_T NumberOfBytes,
    IN ULONG Tag
    );
```

The return value of the allocation function is a pointer to the newly allocated log I/O block.

### -param pfnFreeBuffer [in, optional]

Either **NULL** or a pointer to a caller-supplied function that frees a log I/O block that was previously allocated by *pfnAllocBuffer*. The function has the following prototype:

```cpp
VOID
(*PFREE_FUNCTION) (
    IN PVOID Buffer
    );
```

### -param cbMarshallingBuffer [in]

The size, in bytes, of the individual log I/O blocks that the new marshalling area uses. This must be a multiple of the sector size on the stable storage medium. The sector size is the *lpBytesPerSector* value returned from **GetDiskFreeSpace**.

### -param cMaxWriteBuffers [in]

The maximum number of I/O blocks that can be allocated at one time for write operations. This parameter affects the frequency of data flushes. If you do not need to control the frequency of data flushes, set this parameter to INFINITE.

### -param cMaxReadBuffers [in]

The maximum number of log I/O blocks that can be allocated at one time for read operations.

### -param ppvMarshalContext [out]

A pointer to a variable that receives a pointer to an opaque context that represents the new marshalling area.

## -returns

**ClfsCreateMarshallingArea** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

The *pfnAllocBuffer* and *pfnFreeBuffer* parameters must both point to caller-allocated functions, or they must both be **NULL**. If they are both **NULL**, CLFS provides default functions for allocating and freeing log I/O blocks.

Before calling **ClfsCreateMarshallingArea**, you must add at least two containers to the underlying log by calling [ClfsAddLogContainer](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer) or [ClfsAddLogContainerSet](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset).

For an explanation of CLFS concepts and terminology, see [Common Log File System](/windows-hardware/drivers/kernel/using-common-log-file-system).

## -see-also

[ClfsAddLogContainer](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainer)

[ClfsAddLogContainerSet](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsaddlogcontainerset)

[ClfsCreateLogFile](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile)

[ClfsDeleteMarshallingArea](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsdeletemarshallingarea)

[**LOG_FILE_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
