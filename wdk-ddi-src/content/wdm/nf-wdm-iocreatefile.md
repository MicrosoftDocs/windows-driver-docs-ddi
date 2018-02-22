---
UID: NF:wdm.IoCreateFile
title: IoCreateFile function
author: windows-driver-content
description: The IoCreateFile routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object.
old-location: kernel\iocreatefile.htm
old-project: kernel
ms.assetid: 928f16d4-19cb-4d80-96a6-d25357bfdc30
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k104_7221dba8-910f-439a-acdf-5a6ca4fcd49a.xml, IoCreateFile routine [Kernel-Mode Driver Architecture], kernel.iocreatefile, IoCreateFile, wdm/IoCreateFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCreateFile
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCreateFile function


## -description


The <b>IoCreateFile</b> routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object.


## -syntax


````
NTSTATUS IoCreateFile(
  _Out_    PHANDLE            FileHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     POBJECT_ATTRIBUTES ObjectAttributes,
  _Out_    PIO_STATUS_BLOCK   IoStatusBlock,
  _In_opt_ PLARGE_INTEGER     AllocationSize,
  _In_     ULONG              FileAttributes,
  _In_     ULONG              ShareAccess,
  _In_     ULONG              Disposition,
  _In_     ULONG              CreateOptions,
  _In_opt_ PVOID              EaBuffer,
  _In_     ULONG              EaLength,
  _In_     CREATE_FILE_TYPE   CreateFileType,
  _In_opt_ PVOID              InternalParameters,
  _In_     ULONG              Options
);
````


## -parameters




### -param FileHandle [out]

A pointer to a variable that receives the file handle if the call is successful. The driver must close the handle with <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> once the handle is no longer in use.


### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the type of access that the caller requires to the file or directory. See <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> for a description of the possible values for this parameter.


### -param ObjectAttributes [in]

A pointer to a structure that specifies the object's attributes, which has already been initialized with <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>. If the caller is not running in the system process context, it must set the OBJ_KERNEL_HANDLE attribute for <i>ObjectAttributes</i>.


### -param IoStatusBlock [out]

A pointer to a variable that receives the final completion status and information about the requested operation. On return from <b>IoCreateFile</b>, the <b>Information</b> member contains one of the following values:

<ul>
<li>
FILE_CREATED

</li>
<li>
FILE_OPENED

</li>
<li>
FILE_OVERWRITTEN

</li>
<li>
FILE_SUPERSEDED

</li>
<li>
FILE_EXISTS

</li>
<li>
FILE_DOES_NOT_EXIST

</li>
</ul>

### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size in bytes for the file. A nonzero value has no effect unless the file is being created, overwritten, or superseded.


### -param FileAttributes [in]

Explicitly specified attributes are applied only when the file is created, superseded, or, in some cases, overwritten. By default, this value is FILE_ATTRIBUTE_NORMAL, which can be overridden by an ORed combination of one or more FILE_ATTRIBUTE_<i>XXX</i> flags, which are defined in Wdm.h. For a list of flags that can be used with <b>IoCreateFile</b>, see <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> in the Microsoft Windows SDK documentation.


### -param ShareAccess [in]

Specifies the type of share access that the caller would like to the file, as zero, or as one or a combination of the following:

<table>
<tr>
<th>ShareAccess flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
The file can be opened for read access by other threads' calls to <b>IoCreateFile</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
The file can be opened for write access by other threads' calls to <b>IoCreateFile</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
The file can be opened for delete access by other threads' calls to <b>IoCreateFile</b>.

</td>
</tr>
</table>
 

Device and intermediate drivers usually set <i>ShareAccess</i> to zero, which gives the caller exclusive access to the open file.


### -param Disposition [in]

Specifies what to do, depending on whether the file already exists, as one of the following:

<table>
<tr>
<th>Disposition values</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SUPERSEDE

</td>
<td>
If the file already exists, replace it with the given file. If it does not, create the given file. 

</td>
</tr>
<tr>
<td>
FILE_CREATE 

</td>
<td>
If the file already exists, fail the request and do not create or open the given file. If it does not, create the given file.

</td>
</tr>
<tr>
<td>
FILE_OPEN 

</td>
<td>
If the file already exists, open it instead of creating a new file. If it does not, fail the request and do not create a new file.

</td>
</tr>
<tr>
<td>
FILE_OPEN_IF

</td>
<td>
If the file already exists, open it. If it does not, create the given file.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE

</td>
<td>
If the file already exists, open it and overwrite it. If it does not, fail the request.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE_IF

</td>
<td>
If the file already exists, open it and overwrite it. If it does not, create the given file.

</td>
</tr>
</table>
 


### -param CreateOptions [in]

Specifies the options to be applied when creating or opening the file, as a compatible combination of the following flags:

<table>
<tr>
<th>CreateOptions flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_DIRECTORY_FILE

</td>
<td>
The file being created or opened is a directory file. With this flag, the <i>Disposition</i> parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. With this flag, other compatible <i>CreateOptions</i> flags include only the following: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file being opened must not be a directory file or this call will fail. The file object being opened can represent a data file, a logical, virtual, or physical device, or a volume.

</td>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, file system drivers (FSDs), and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete.

</td>
</tr>
<tr>
<td>
FILE_SEQUENTIAL_ONLY

</td>
<td>
All accesses to the file will be sequential.

</td>
</tr>
<tr>
<td>
FILE_RANDOM_ACCESS

</td>
<td>
Accesses to the file can be random, so no sequential read-ahead operations should be performed on the file by FSDs or the system.

</td>
</tr>
<tr>
<td>
FILE_NO_INTERMEDIATE_BUFFERING

</td>
<td>
The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the <i>DesiredAccess</i> FILE_APPEND_DATA flag.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the file are performed synchronously. Waits in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set.

</td>
</tr>
<tr>
<td>
FILE_CREATE_TREE_CONNECTION

</td>
<td>
Create a tree connection for this file in order to open it over the network. This flag is irrelevant to device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_COMPLETE_IF_OPLOCKED

</td>
<td>
Complete this operation immediately with an alternate success code if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file over the network. This flag is irrelevant to device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_NO_EA_KNOWLEDGE

</td>
<td>
If the extended attributes on an existing file being opened indicate that the caller must understand EAs to properly interpret the file, fail this request because the caller does not understand how to deal with EAs. Device and intermediate drivers can ignore this flag.

</td>
</tr>
<tr>
<td>
FILE_OPEN_REPARSE_POINT

</td>
<td>
Open a file with a reparse point and bypass normal reparse point processing for the file. For more information, see the following Remarks section.

</td>
</tr>
<tr>
<td>
FILE_DELETE_ON_CLOSE

</td>
<td>
Delete the file when the last handle to it is passed to <b>ZwClose</b>.

</td>
</tr>
<tr>
<td>
FILE_OPEN_BY_FILE_ID

</td>
<td>
The file name specified in the <i>ObjectAttributes</i> parameter includes the 8-byte file reference number for the file. This number is assigned by the file system and is file-system-specific. If the file is a reparse point, the file name also includes the name of a device. Note: The FAT file system does not support FILE_OPEN_BY_FILE_ID.

</td>
</tr>
<tr>
<td>
FILE_OPEN_FOR_BACKUP_INTENT

</td>
<td>
The file is being opened for backup intent, hence, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input <i>DesiredAccess</i> against the file's security descriptor. This flag is irrelevant to device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_OPEN_REQUIRING_OPLOCK 

</td>
<td>
The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create operation will fail with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create operation would break an existing oplock.

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2, and later Windows operating systems.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_RESERVE_OPFILTER

</td>
<td>
This flag allows an application to request a filter opportunistic lock (oplock) to prevent other applications from getting share violations. If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED. For more information, see the following Remarks section.

</td>
</tr>
</table>
 


### -param EaBuffer [in, optional]

For device and intermediate drivers, this parameter must be a <b>NULL</b> pointer.


### -param EaLength [in]

For device and intermediate drivers, this parameter must be zero.


### -param CreateFileType [in]

Drivers must set this parameter to <b>CreateFileTypeNone</b>.


### -param InternalParameters [in, optional]

Drivers must set this parameter to <b>NULL</b>.


### -param Options [in]

Specifies options to be used during the creation of the create request. These options can be from the following list:

<table>
<tr>
<th>Options flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IO_NO_PARAMETER_CHECKING

</td>
<td>
Indicates that the parameters for this call should not be validated before attempting to issue the create request. Driver writers should use this flag with caution as certain invalid parameters can cause a system failure. For more information, see Remarks.

</td>
</tr>
<tr>
<td>
IO_FORCE_ACCESS_CHECK

</td>
<td>
Indicates that the I/O manager must check the operation against the file's security descriptor.

</td>
</tr>
<tr>
<td>
IO_STOP_ON_SYMLINK

</td>
<td>
The I/O manager or the file system will return STATUS_STOPPED_ON_SYMLINK if a symbolic link is encountered while opening or creating the file.

</td>
</tr>
<tr>
<td>
IO_OPEN_TARGET_DIRECTORY

</td>
<td>
Open the file's parent directory.

</td>
</tr>
</table>
 


## -returns



<b>IoCreateFile</b> either returns STATUS_SUCCESS or an appropriate error status. If it returns an error status, the caller can find additional information about the cause of the failure by checking the <i>IoStatusBlock</i>.




## -remarks



<div class="alert"><b>Note</b>  The Windows Vista <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine is similar to the <b>IoCreateFile</b> routine but provides greater functionality than the <b>IoCreateFile</b> routine, including access to extra create parameters (ECPs), device objects, and transaction information.</div>
<div> </div>
The handle, obtained by <b>IoCreateFile</b>, can be used by subsequent calls to manipulate data within the file or the file object's state or attributes.

There are two alternate ways to specify the name of the file to be created or opened with <b>IoCreateFile</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>

</li>
<li>
As pathname relative to the directory file represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>

</li>
</ol>
Certain <i>DesiredAccess</i> flags and combinations of flags have the following effects:

<ul>
<li>
For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i>, the SYNCHRONIZE flag must be set. Otherwise, a caller that is a device or intermediate driver must synchronize an I/O completion by using an event object.

</li>
<li>
If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about writes to the file is ignored. However, the file will automatically be extended as necessary for this type of write operation.

</li>
<li>
Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well.

</li>
<li>
If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot directly read or write any data in the file using the returned <i>FileHandle</i>: that is, all operations on the file occur through the system pager in response to instruction and data accesses. Device and intermediate drivers should not set the FILE_EXECUTE flag in <i>DesiredAccess</i>.

</li>
</ul>
The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of <b>IoCreateFile</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file: that is, the original caller is given exclusive access to the file.

In order for a shared file to be successfully opened, the requested <i>DesiredAccess</i> to the file must be compatible with both the <i>DesiredAccess</i> and <i>ShareAccess</i> specifications of all preceding opens that have not yet been released with <b>ZwClose</b>. That is, the <i>DesiredAccess</i> specified to <b>IoCreateFile</b> for a given file must not conflict with the accesses that other openers of the file have disallowed.

The <i>Disposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to <b>IoCreateFile</b> with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that, if the file has already been opened by another thread, it opened the file by specifying a <i>ShareAccess </i>parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The <i>Disposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>IoCreateFile</b> is called with a existing file and either of these <i>Disposition</i> values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

<ul>
<li>
The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i>.

</li>
<li>
The specified file attributes are logically ORed with those already on the file. This implies that, if the file has already been opened by another thread, a subsequent caller of <b>IoCreateFile</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file.

</li>
</ul>
The <i>CreateOptions</i> FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent <i>CreateOptions</i> or <i>Disposition</i> value, the call to <b>IoCreateFile</b> will fail.

The <i>CreateOptions</i> FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to the <b>Zw<i>Xxx</i>File</b> routines, including the following:

<ul>
<li>
Any optional <i>ByteOffset</i> passed to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be an integral of the sector size.

</li>
<li>
The <i>Length</i> passed to <b>ZwReadFile</b> or <b>ZwWriteFile</b>, must be an integral of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

</li>
<li>
Buffers must be aligned in accordance with the alignment requirement of the underlying device. This information can be obtained by calling <b>IoCreateFile</b> to get a handle for the file object that represents the physical device, and, then, calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> with that handle. For a list of the system FILE_<i>XXX</i>_ALIGNMENT values, see <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.

</li>
<li>
Calls to <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is an integral of the sector size.

</li>
</ul>
The <i>CreateOptions</i> FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, which are mutually exclusive as their names suggest, specify that all I/O operations on the file are to be synchronous as long as they occur through the file object referred to by the returned <i>FileHandle</i>. All I/O on such a file is serialized across all threads using the returned handle. With either of these <i>CreateOptions</i>, the <i>DesiredAccess</i> SYNCHRONIZE flag must be set so that the I/O manager will use the file object as a synchronization object. With either of these <i>CreateOptions</i> set, the I/O manager maintains the "file position context" for the file object, an internal, current file position offset. This offset can be used in calls to <b>ZwReadFile</b> and <b>ZwWriteFile</b>. Its position also can be queried or set with <b>ZwQueryInformationFile</b> and <b>ZwSetInformationFile</b>.

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is <u>not</u> specified and <b>IoCreateFile</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file. If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does <u>not</u> occur and <b>IoCreateFile</b> attempts to directly open the reparse point file. In either case, if the open operation was successful, <b>IoCreateFile</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>IoCreateFile</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>IoCreateFile</b> and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

An application that uses the FILE_OPEN_REQUIRING_OPLOCK flag must request an oplock after this call succeeds, or all subsequent attempts to open the file will be blocked without the benefit of normal oplock processing. Similarly, if this call succeeds but the subsequent oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later versions of Windows. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.</div>
<div> </div>
The <i>CreateOptions</i> flag, FILE_RESERVE_OPFILTER, allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only useful for filter oplocks. To use it, you must follow these steps:

<ol>
<li>
Issue a create request with <i>CreateOptions</i> of FILE_RESERVE_OPFILTER, <i>DesiredAccess</i> of exactly FILE_READ_ATTRIBUTES, and <i>ShareAccess</i> of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.

<ul>
<li>
If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.

</li>
<li>
If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.

</li>
</ul>
</li>
<li>
If the create request succeeds, request an oplock.

</li>
<li>
Open another handle to the file to do I/O.

</li>
</ol>
Step 3 makes this practical only for filter oplocks. The handle opened in step 3 can have a <i>DesiredAccess</i> that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any <i>DesiredAccess</i> greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

The <i>Options</i> IO_NO_PARAMETER_CHECKING flag can be useful if a kernel-mode create request is issued in the context of an operation initiated by a user-mode application. Because the request occurs within a user-mode context, the I/O manager, by default, probes the supplied parameter values, which can cause an access violation if the parameters are kernel-mode addresses. This flag enables the caller to override this default behavior and avoid the access violation.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>IoCreateFile</b>. This restricts the use of the handle returned by <b>IoCreateFile</b> to processes running only in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. Drivers can call <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to set the OBJ_KERNEL_HANDLE attribute as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>InitializeObjectAttributes(&amp;ObjectAttributes, NULL, OBJ_KERNEL_HANDLE, NULL, NULL);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCreateFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

