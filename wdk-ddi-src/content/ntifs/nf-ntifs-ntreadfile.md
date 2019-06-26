---
UID: NF:ntifs.NtReadFile
title: NtReadFile function (ntifs.h)
description: The ZwReadFile routine reads data from an open file.
old-location: kernel\zwreadfile.htm
tech.root: kernel
ms.assetid: 0f1ec015-bda6-45fe-973d-be414aece918
ms.date: 04/30/2018
ms.keywords: NtReadFile, ZwReadFile, ZwReadFile routine [Kernel-Mode Driver Architecture], k111_5cf3ebe2-7c2f-4998-b441-7d2aa2eb091f.xml, kernel.zwreadfile, wdm/NtReadFile, wdm/ZwReadFile
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, HwStorPortProhibitedDDIs
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
- ZwReadFile
- NtReadFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtReadFile function


## -description


The <b>NtReadFile</b> routine reads data from an open file. 


## -parameters




### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntopenfile">NtOpenFile</a>. 


### -param Event [in, optional]

Optionally, a handle to an event object to set to the signaled state after the read operation completes. Device and intermediate drivers should set this parameter to <b>NULL</b>.


### -param ApcRoutine [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param ApcContext [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested read operation. The <b>Information</b> member receives the number of bytes actually read from the file.


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the data read from the file.


### -param Length [in]

The size, in bytes, of the buffer pointed to by <i>Buffer</i>.


### -param ByteOffset [in, optional]

Pointer to a variable that specifies the starting byte offset in the file where the read operation will begin. If an attempt is made to read beyond the end of the file, <b>NtReadFile</b> returns an error.

If the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a> set either of the <b>CreateOptions</b> flags FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT, the I/O Manager maintains the current file position. If so, the caller of <b>NtReadFile</b> can specify that the current file position offset be used instead of an explicit <b>ByteOffset</b> value. This specification can be made by using one of the following methods:

<ul>
<li>
Specify a pointer to a LARGE_INTEGER value with the <b>HighPart</b> member set to -1 and the <b>LowPart</b> member set to the system-defined value FILE_USE_FILE_POINTER_POSITION.

</li>
<li>
Pass a <b>NULL</b> pointer for <i>ByteOffset</i>.

</li>
</ul>
<b>NtReadFile</b> updates the current file position by adding the number of bytes read when it completes the read operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit <i>ByteOffset</i> value to <b>NtReadFile</b>. Doing this automatically changes the current file position to that <i>ByteOffset</i> value, performs the read operation, and then updates the position according to the number of bytes actually read. This technique gives the caller atomic seek-and-read service.


### -param Key [in, optional]

Device and intermediate drivers should set this pointer to <b>NULL</b>. 


## -returns



<b>NtReadFile</b> returns either STATUS_SUCCESS or the appropriate NTSTATUS error code.




## -remarks



Callers of <b>NtReadFile</b> must have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a> with the FILE_READ_DATA or GENERIC_READ value set in the <i>DesiredAccess</i> parameter.

If the preceding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> set the FILE_NO_INTERMEDIATE_BUFFERING flag in the <i>CreateOptions</i> parameter to <b>NtCreateFile</b>, the <i>Length</i> and <i>ByteOffset</i> parameters to <b>NtReadFile</b> must be multiples of the sector size. 

<b>NtReadFile</b> begins reading from the given <i>ByteOffset</i> or the current file position into the given <i>Buffer</i>. It terminates the read operation under one of the following conditions:

<ul>
<li>
The buffer is full because the number of bytes specified by the <i>Length</i> parameter has been read. Therefore, no more data can be placed into the buffer without an overflow.

</li>
<li>
The end of file is reached during the read operation, so there is no more data in the file to be transferred into the buffer.

</li>
</ul>
If the caller opened the file with the SYNCHRONIZE flag set in <i>DesiredAccess</i>, the calling thread can synchronize to the completion of the read operation by waiting on the file handle, <i>FileHandle</i>. The handle is signaled each time that an I/O operation that was issued on the handle completes. However, the caller must not wait on a handle that was opened for synchronous file access (FILE_SYNCHRONOUS_IO_NONALERT or FILE_SYNCHRONOUS_IO_ALERT). In this case, <b>NtReadFile</b> waits on behalf of the caller and does not return until the read operation is complete. The caller can safely wait on the file handle only if all three of the following conditions are met:

<ul>
<li>
The handle was opened for asynchronous access (that is, neither FILE_SYNCHRONOUS_IO_<b>XXX</b> flag was specified). 

</li>
<li>
The handle is being used for only one I/O operation at a time. 

</li>
<li>
<b>NtReadFile</b> returned STATUS_PENDING. 

</li>
</ul>
A driver should call <b>NtReadFile</b> in the context of the system process if any of the following conditions exist:

<ul>
<li>
The driver created the file handle that it passes to <b>NtReadFile</b>.

</li>
<li>
<b>NtReadFile</b> will notify the driver of I/O completion by means of an event that the driver created.

</li>
<li>
<b>NtReadFile</b> will notify the driver of I/O completion by means of  an APC callback routine that the driver passes to <b>NtReadFile</b>. 

</li>
</ul>
File and event handles are valid only in the process context where the handles are created. Therefore, to avoid security holes, the driver should create any file or event handle that it passes to <b>NtReadFile</b> in the context of the system process rather than the context of the process that the driver is in.

Likewise, <b>NtReadFile</b> should be called in the context of the system process if it notifies the driver of I/O completion by means of an APC, because APCs are always fired in the context of the thread that issues the I/O request. If the driver calls <b>NtReadFile</b> in the context of a process other than the system one, the APC could be delayed indefinitely, or it might not fire at all.

For more information about working with files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-files-in-a-driver">Using Files in a Driver</a>.

Callers of <b>NtReadFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntreadfile">NtReadFile</a>" instead of "<b>ZwReadFile</b>".</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntwritefile">ZwWriteFile</a>
 

 

