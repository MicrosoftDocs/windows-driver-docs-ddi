---
UID: NF:ntifs.ZwUnlockFile
title: ZwUnlockFile function (ntifs.h)
description: The ZwUnlockFile routine unlocks a byte-range lock in a file.
old-location: kernel\zwunlockfile.htm
tech.root: kernel
ms.assetid: dca3023b-99d5-471a-a5a2-8453c367ce9b
ms.date: 04/30/2018
keywords: ["ZwUnlockFile function"]
ms.keywords: NtUnlockFile, ZwUnlockFile, ZwUnlockFile routine [Kernel-Mode Driver Architecture], k111_a77fe0ba-5252-4441-aaad-67d2bbae01cb.xml, kernel.zwunlockfile, ntifs/NtUnlockFile, ntifs/ZwUnlockFile
f1_keywords:
 - "ntifs/ZwUnlockFile"
 - "ZwUnlockFile"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwUnlockFile
- NtUnlockFile
targetos: Windows
req.typenames: 
---

# ZwUnlockFile function


## -description


The <b>ZwUnlockFile</b> routine unlocks a byte-range lock in a file.


## -parameters




### -param FileHandle 
[in]
A handle for the file object that represents the file whose byte range is to be unlocked.


### -param IoStatusBlock 
[out]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that contains the final status.


### -param ByteOffset 
[in]
A pointer to a variable that specifies the starting byte offset for the byte range to be unlocked.


### -param Length 
[in]
A pointer to a variable that specifies the length, in bytes, of the byte range to unlock.


### -param Key 
[in]
The caller-assigned value used to describe groups of related locks. This value should be set to zero.


## -returns



The <b>ZwUnlockFile</b> routine returns STATUS_SUCCESS on success or an appropriate NTSTATUS value. Possible NTSTATUS values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RANGE_NOT_LOCKED</b></dt>
</dl>
</td>
<td width="60%">
The byte range specified is not locked.

</td>
</tr>
</table>
 




## -remarks



The <b>ZwUnlockFile</b> routine takes a range of bytes as specified by the <i>ByteOffset</i> and <i>Length</i> arguments. This range must be identical to a range of bytes in the file that was previously locked with a single call to the <b>ZwUnlockFile</b> routine. It is not possible to unlock two previously locked adjacent ranges with a single call to <b>ZwUnlockFile</b>. It is also not possible to unlock part of a range that was previously locked with a single call to the <b>ZwUnlockFile</b> routine.

Callers of <b>ZwUnlockFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwUnlockFile</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff567118">NtUnlockFile</a>" instead of "<b>ZwUnlockFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566474">ZwLockFile</a>
 

 

