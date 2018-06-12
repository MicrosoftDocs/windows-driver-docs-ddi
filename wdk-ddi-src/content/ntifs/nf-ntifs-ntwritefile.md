---
UID: NF:ntifs.NtWriteFile
title: NtWriteFile function
author: windows-driver-content
description: The ZwWriteFile routine writes data to an open file.
old-location: kernel\zwwritefile.htm
old-project: kernel
ms.assetid: b64ca88f-f67d-4c92-aa0c-46dbe4970834
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtWriteFile, ZwWriteFile, ZwWriteFile routine [Kernel-Mode Driver Architecture], k111_97437555-3cb5-497b-8ebb-c683771da9f4.xml, kernel.zwwritefile, wdm/NtWriteFile, wdm/ZwWriteFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwWriteFile
-	NtWriteFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtWriteFile function


## -description


The <b>ZwWriteFile</b> routine writes data to an open file.


## -parameters




### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">NtOpenFile</a>. 


### -param Event [in, optional]

Optionally, a handle to an event object to set to the signaled state after the write operation completes. Device and intermediate drivers should set this parameter to <b>NULL</b>.


### -param ApcRoutine [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param ApcContext [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested write operation. The <b>Information</b> member receives the number of bytes actually written to the file.


### -param Buffer [in]

Pointer to a caller-allocated buffer that contains the data to write to the file.


### -param Length [in]

The size, in bytes, of the buffer pointed to by <i>Buffer</i>.


### -param ByteOffset [in, optional]

Pointer to a variable that specifies the starting byte offset in the file for beginning the write operation. If <i>Length</i> and <i>ByteOffset</i> specify a write operation past the current end-of-file mark, <b>NtWriteFile</b> automatically extends the file and updates the end-of-file mark; any bytes that are not explicitly written between such old and new end-of-file marks are defined to be zero.

If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> set only the <i>DesiredAccess</i> flag FILE_APPEND_DATA, <i>ByteOffset</i> is ignored. Data in the given <i>Buffer</i>, for <i>Length</i> bytes, is written starting at the current end of file.

If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> set either of the <i>CreateOptions</i> flags, FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT, the I/O Manager maintains the current file position. If so, the caller of <b>NtWriteFile</b> can specify that the current file position offset be used instead of an explicit <i>ByteOffset</i> value. This specification can be made by using one of the following methods:

<ul>
<li>
Specify a pointer to a LARGE_INTEGER value with the <b>HighPart</b> member set to -1 and the <b>LowPart</b> member set to the system-defined value FILE_USE_FILE_POINTER_POSITION.

</li>
<li>
Pass a <b>NULL</b> pointer for <i>ByteOffset</i>.

</li>
</ul>
<b>NtWriteFile</b> updates the current file position by adding the number of bytes written when it completes the write operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit <i>ByteOffset</i> value to <b>NtWriteFile</b>. Doing this automatically changes the current file position to that <i>ByteOffset</i>value, performs the write operation, and then updates the position according to the number of bytes actually written. This technique gives the caller atomic seek-and-write service.

It is also possible to cause a write operation to start at the current end of file by specifying for <i>ByteOffset</i> a pointer to a LARGE_INTEGER value with <b>HighPart</b> set to -1 and <b>LowPart</b> set to FILE_WRITE_TO_END_OF_FILE. This works regardless of whether the I/O Manager is maintaining the current file position.


### -param Key [in, optional]

Device and intermediate drivers should set this pointer to <b>NULL</b>. 


## -returns



<b>NtWriteFile</b> returns STATUS_SUCCESS on success or the appropriate NTSTATUS error code on failure.




## -remarks



Callers of <b>NtWriteFile</b> must have already called <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> with the FILE_WRITE_DATA, FILE_APPEND_DATA, or GENERIC_WRITE flag set in the <i>DesiredAccess</i> parameter. Note that having only FILE_APPEND_DATA access to a file does not allow the caller to write anywhere in the file except at the current end-of-file mark, while having FILE_WRITE_DATA access to a file does not preclude the caller from writing to or beyond the end of a file.

If the preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> set the <i>CreateOptions</i> flag FILE_NO_INTERMEDIATE_BUFFERING, the <i>Length</i> and <i>ByteOffset</i> parameters to <b>NtWriteFile</b> must be an integral of the sector size. For more information, see <b>NtCreateFile</b>.

<b>NtWriteFile</b> begins the write operation to the file at <i>ByteOffset</i>, at the current file position, or at the end-of-file mark. It terminates the write operation when it has written <i>Length</i> bytes from <i>Buffer</i>. If necessary, it extends the length of the file and resets the end-of-file mark.

If the caller opened the file with the <i>DesiredAccess</i> SYNCHRONIZE flag set, the caller can wait for this routine to set the given <i>FileHandle</i> to the signaled state.

Drivers should call <b>NtWriteFile</b> in the context of the system process in three cases:

<ol>
<li>
The driver creates the file handle that it passes to <b>NtWriteFile</b>.

</li>
<li>
<b>NtWriteFile</b> notifies the driver of I/O completion by means of an event created by the driver.

</li>
<li>
<b>NtWriteFile</b> notifies the driver of I/O completion by means of an APC callback routine that the driver passes to <b>NtWriteFile</b>.

</li>
</ol>
File and event handles are only valid in the process context where the handles are created. Therefore, to avoid security holes, the driver should create any file or event handle that it passes to <b>NtWriteFile</b> in the context of the system process instead of the process context that the driver is in.

Likewise, <b>NtWriteFile</b> should be called in the context of the system process if it notifies the driver of I/O completion by means of an APC, because APCs are always fired in the context of the thread issuing the I/O request. If the driver calls <b>NtWriteFile</b> in the context of a process other than the system process, the APC could be delayed indefinitely, or it might not fire at all as the originating thread may never enter an alertable wait state.

For more information about working with files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Callers of <b>NtWriteFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557714">NtWriteFile</a>" instead of "<b>ZwWriteFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

