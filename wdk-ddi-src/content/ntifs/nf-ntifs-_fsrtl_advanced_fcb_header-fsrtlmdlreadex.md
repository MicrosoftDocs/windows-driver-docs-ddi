---
UID: NF:ntifs.FsRtlMdlReadEx
title: FsRtlMdlReadEx function (ntifs.h)
description: Learn more about the FsRtlMdlReadEx routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlMdlReadEx function"]
ms.keywords: FsRtlMdlReadEx, ifsk.fsrtlmdlreadex, ntifs/FsRtlMdlReadEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlMdlReadEx
 - ntifs/FsRtlMdlReadEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlMdlReadEx
dev_langs:
 - c++
---

# FsRtlMdlReadEx function

## -description

The **FsRtlMdlReadEx** routine performs a fast cached MDL read.  If the requested data is not cached, the routine reverts to an IRP based MDL read operation.

## -parameters

### -param FileObject [in]

A pointer to the file object.

### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.

### -param Length [in]

The length in bytes of the data to read from the cache.

### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.

### -param MdlChain [out]

An address of a variable that receives a pointer to a linked list of memory descriptor lists (MDLs). **MdlChain** must be initialized to **NULL** before the call to **FsRtlMdlReadEx**.

### -param IoStatus [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that, on output, contains the status of the transfer. If the operation succeeds, **IoStatus.Status** is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. **IoStatus.Information** is set to the actual number of bytes that the routine successfully locked.

## -returns

**FsRtlMdlReadEx** returns **STATUS_SUCCESS** or an appropriate **NTSTATUS** value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | The IRP for an the IRP based read could not be allocated. |

## -remarks

If fast I/O is available from the file system, the **FsRtlMdlReadEx** routine will bypass the usual IRP read mechanism and return a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read. If fast I/O is not enabled, **FsRtlMdlReadEx** will generate a synchronous IRP based MDL read and return the MDLs from the request.

The pages described by the MDLs are locked in memory, but not mapped in system space. The caller can perform this mapping by calling [**MmGetSystemAddressForMdlSafe**](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md).

Similar to [**CcMdlRead**](/previous-versions/ff539159(v=vs.85)), the **FsRtlMdlReadEx** routine locks the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the **CcMdlReadComplete** routine.

## -see-also

[**CcMdlRead**](/previous-versions/ff539159(v=vs.85))

[**CcMdlReadComplete**](nf-ntifs-ccmdlreadcomplete.md)

[**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md)

[**MmGetSystemAddressForMdlSafe**](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md)
