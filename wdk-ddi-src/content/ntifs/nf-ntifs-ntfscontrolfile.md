---
UID: NF:ntifs.NtFsControlFile
title: NtFsControlFile function
author: windows-driver-content
description: The ZwFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.
old-location: kernel\zwfscontrolfile.htm
tech.root: kernel
ms.assetid: 2e98d111-5af5-4854-9b58-f5237ba913e7
ms.date: 04/30/2018
ms.keywords: NtFsControlFile, ZwFsControlFile, ZwFsControlFile routine [Kernel-Mode Driver Architecture], k111_5da20655-11b0-4366-bca2-8cee3aadbeab.xml, kernel.zwfscontrolfile, ntifs/NtFsControlFile, ntifs/ZwFsControlFile
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	ZwFsControlFile
-	NtFsControlFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtFsControlFile function


## -description


The <b>NtFsControlFile</b> routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.


## -parameters




### -param FileHandle [in]

Handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">NtCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">NtOpenFile</a> for the file object representing the file or directory on which the specified action is to be performed. The file object must have been opened for asynchronous I/O if the caller specifies an <i>Event</i>, <i>ApcRoutine</i>, and an APC context (in <i>ApcContext</i>), or a completion context (in <i>ApcContext</i>).


### -param Event [in, optional]

Handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if the caller will wait for the <i>FileHandle</i> to be set to the Signaled state.


### -param ApcRoutine [in, optional]

Address of a caller-supplied APC routine to be called when the requested operation completes. This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if there is an I/O completion object associated with the file object.


### -param ApcContext [in, optional]

Pointer to a caller-determined context area. This parameter value is used as the APC context if the caller supplies an APC, or is used as the completion context if an I/O completion object has been associated with the file object. When the operation completes, either the APC context is passed to the APC, if one was specified, or the completion context is included as part of the completion message that the I/O Manager posts to the associated I/O completion object.

This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if <i>ApcRoutine</i> is <b>NULL</b> and there is no I/O completion object associated with the file object.


### -param IoStatusBlock [out]

Pointer to an IO_STATUS_BLOCK structure that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the <i>OutputBuffer</i> is returned in the <b>Information</b> member of this structure.


### -param FsControlCode [in]

FSCTL_<i>XXX</i> code that indicates which file system control operation is to be carried out. The value of this parameter determines the formats and required lengths of the <i>InputBuffer</i> and <i>OutputBuffer</i>, as well as which of the following parameter pairs are required. For detailed information about the system-defined FSCTL_<i>XXX</i> codes, see the "Remarks" section of the reference entry for <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> in the Microsoft Windows SDK documentation.


### -param InputBuffer [in, optional]

Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If <i>FsControlCode</i> specifies an operation that does not require input data, this pointer is optional and can be <b>NULL</b>. 


### -param InputBufferLength [in]

Size, in bytes, of the buffer at <i>InputBuffer</i>. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>.


### -param OutputBuffer [out, optional]

Pointer to a caller-allocated output buffer in which information is returned from the target driver. If <i>FsControlCode</i> specifies an operation that does not produce output data, this pointer is optional and can be <b>NULL</b>.


### -param OutputBufferLength [in]

Size, in bytes, of the buffer at <i>OutputBuffer</i>. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>.


## -returns



<b>NtFsControlFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:




## -remarks



<b>NtFsControlFile</b> provides a consistent view of the input and output data to the system and to kernel-mode drivers, while providing applications and underlying drivers with a driver-dependent method of specifying a communications interface.

If the caller opened the file for asynchronous I/O (with neither FILE_SYNCHRONOUS_<i>XXX</i> create/open option set), the specified event, if any, will be set to the signaled state when the device control operation completes. Otherwise, the file object specified by <i>FileHandle</i> will be set to the signaled state. If an <i>ApcRoutine</i> was specified, it is called with the <i>ApcContext</i> and <i>IoStatusBlock</i> pointers.

The following FSCTL codes are currently documented for kernel-mode drivers:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>


For more information about system-defined FSCTL_<i>XXX</i> codes, see the "Remarks" section of the reference entry for <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> in the Microsoft Windows SDK documentation. 

For more information about system-defined IOCTL_<i>XXX</i> codes, and about defining driver-specific IOCTL_<i>XXX</i> or FSCTL_<i>XXX</i> values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a> in the <i>Kernel Mode Architecture Guide</i> and <i>Device Input and Output Control Codes</i> in the Windows SDK documentation. 

Minifilters should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a> instead of <b>NtFsControlFile</b>. 

Callers of <b>NtFsControlFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>NtFsControlFile</b> function occurs in user mode, you should use the name "<b>NtFsControlFile</b>" instead of "<b>ZwFsControlFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549236">IoGetFunctionCodeFromCtlCode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548443">IoIsOperationSynchronous</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566441">ZwDeviceIoControlFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>
 

 

