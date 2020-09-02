---
UID: NF:ntifs.NtLockFile
title: NtLockFile function (ntifs.h)
description: The NtLockFile routine requests a byte-range lock for the specified file.
old-location: kernel\zwlockfile.htm
tech.root: kernel
ms.assetid: d5d4d13c-93d9-4531-85ff-d3fa0e52ecc1
ms.date: 04/30/2018
keywords: ["NtLockFile function"]
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
 - NtLockFile
 - ntifs/NtLockFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwLockFile
 - NtLockFile
---

# NtLockFile function


## -description

The <b>NtLockFile</b> routine requests a byte-range lock for the specified file.

## -parameters

### -param FileHandle 

[in]
A handle for the file on which a byte-range lock is requested.

### -param Event 

[in, optional]
A handle to a caller-created event. If not <b>NULL</b>, the caller is placed into a wait state until the operation succeeds, at which time the event is set into the Signaled state.

### -param ApcRoutine 

[in, optional]
A pointer to a caller-supplied APC routine that is executed after the operation completes. Can be <b>NULL</b>.

### -param ApcContext 

[in, optional]
A pointer to a caller-specified context for the APC routine. This value is passed to the APC routine when it is executed. Can be <b>NULL</b>.

### -param IoStatusBlock 

[out]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that contains the final status.

### -param ByteOffset 

[in]
A pointer to a variable that specifies the starting byte offset of the range to lock.

### -param Length 

[in]
A pointer to a variable that specifies the length in bytes of the range to lock.

### -param Key 

[in]
A caller-assigned value used to describe groups of related locks. This value should be set to zero.

### -param FailImmediately 

[in]
If <b>TRUE</b>, immediately return if the file cannot be locked. If <b>FALSE</b>, wait for the lock request to be granted.

### -param ExclusiveLock 

[in]
If <b>TRUE</b>, byte-range lock is exclusive; otherwise, shared lock.

## -returns

The <b>NtLockFile</b> routine returns STATUS_SUCCESS or an appropriate error NTSTATUS value. Possible NTSTATUS values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources exist to grant the byte-range lock for the specified file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The byte-range lock was not granted for the specified file.

</td>
</tr>
</table>

## -remarks

Callers of <b>NtLockFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>NtLockFile</b> function occurs in user mode, you should use the name "<b>NtLockFile</b>" instead of "<b>ZwLockFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567118">ZwUnlockFile</a>

