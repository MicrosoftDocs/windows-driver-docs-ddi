---
UID: NF:ntifs.ZwLockFile
title: ZwLockFile function (ntifs.h)
description: The ZwLockFile routine requests a byte-range lock for the specified file.
old-location: kernel\zwlockfile.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["ZwLockFile function"]
ms.keywords: NtLockFile, ZwLockFile, ZwLockFile routine [Kernel-Mode Driver Architecture], k111_267331a3-5339-46ce-a0b6-d7b2e0aba68f.xml, kernel.zwlockfile, ntifs/NtLockFile, ntifs/ZwLockFile
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwLockFile
 - ntifs/ZwLockFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwLockFile
---

# ZwLockFile function

## -description

The **ZwLockFile** routine requests a byte-range lock for the specified file.

## -parameters

### -param FileHandle [in]

A handle for the file on which a byte-range lock is requested.

### -param Event [in, optional]

A handle to a caller-created event. If not **NULL**, the caller is placed into a wait state until the operation succeeds, at which time the event is set into the Signaled state.

### -param ApcRoutine [in, optional]

A pointer to a caller-supplied APC routine that is executed after the operation completes. Can be **NULL**.

### -param ApcContext [in, optional]

A pointer to a caller-specified context for the APC routine. This value is passed to the APC routine when it is executed. Can be **NULL**.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status.

### -param ByteOffset [in]

A pointer to a variable that specifies the starting byte offset of the range to lock.

### -param Length [in]

A pointer to a variable that specifies the length in bytes of the range to lock.

### -param Key [in]

A caller-assigned value used to describe groups of related locks. This value should be set to zero.

### -param FailImmediately [in]

If **TRUE**, immediately return if the file cannot be locked. If **FALSE**, wait for the lock request to be granted.

### -param ExclusiveLock [in]

If **TRUE**, byte-range lock is exclusive; otherwise, shared lock.

## -returns

The **ZwLockFile** routine returns STATUS_SUCCESS or an appropriate error NTSTATUS value such as one of the following.

| Error code | Description |
| ---------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | Insufficient resources exist to grant the byte-range lock for the specified file. |
| STATUS_LOCK_NOT_GRANTED       | The byte-range lock was not granted for the specified file. |

## -remarks

Callers of **ZwLockFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
>
> If the call to the **ZwLockFile** function occurs in user mode, you should use the name "**NtLockFile**" instead of "**ZwLockFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**ZwUnlockFile**](nf-ntifs-zwunlockfile.md)
