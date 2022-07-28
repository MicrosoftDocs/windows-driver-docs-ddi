---
UID: NF:ntifs.NtUnlockFile
title: NtUnlockFile function (ntifs.h)
description: The NtUnlockFile routine in unlocks a byte-range lock in a file. If the call is in user mode, use the name NtUnlockFile instead of ZwUnlockFile.
old-location: kernel\zwunlockfile.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["NtUnlockFile function"]
ms.keywords: NtUnlockFile, ZwUnlockFile, ZwUnlockFile routine [Kernel-Mode Driver Architecture], k111_a77fe0ba-5252-4441-aaad-67d2bbae01cb.xml, kernel.zwunlockfile, ntifs/NtUnlockFile, ntifs/ZwUnlockFile
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
 - NtUnlockFile
 - ntifs/NtUnlockFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtUnlockFile
---

# NtUnlockFile function

## -description

The **NtUnlockFile** routine unlocks a byte-range lock in a file.

## -parameters

### -param FileHandle [in]

A handle for the file object that represents the file whose byte range is to be unlocked.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status.

### -param ByteOffset [in]

A pointer to a variable that specifies the starting byte offset for the byte range to be unlocked.

### -param Length [in]

A pointer to a variable that specifies the length, in bytes, of the byte range to unlock.

### -param Key [in]

The caller-assigned value used to describe groups of related locks. This value should be set to zero.

## -returns

The **NtUnlockFile** routine returns STATUS_SUCCESS on success or an appropriate NTSTATUS value. Possible NTSTATUS values include:

| Return code | Description |
| ----------- | ----------- |
| STATUS_RANGE_NOT_LOCKED | The byte range specified is not locked. |

## -remarks

The **NtUnlockFile** routine takes a range of bytes as specified by the **ByteOffset** and **Length** arguments. This range must be identical to a range of bytes in the file that was previously locked with a single call to the **NtUnlockFile** routine. It is not possible to unlock two previously locked adjacent ranges with a single call to **NtUnlockFile**. It is also not possible to unlock part of a range that was previously locked with a single call to the **NtUnlockFile** routine.

Callers of **NtUnlockFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled**](/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
> If the call to the **NtUnlockFile** function occurs in kernel mode, you should use the name "[**ZwUnlockFile**](nf-ntifs-zwlockfile.md)" instead of "**NtUnlockFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtLockFile**](nf-ntifs-ntlockfile.md)
