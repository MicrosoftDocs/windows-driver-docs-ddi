---
UID: NF:ntifs.NtCreateFile
title: NtCreateFile function
author: windows-driver-content
description: The ZwCreateFile routine creates a new file or opens an existing file.
old-location: kernel\zwcreatefile.htm
old-project: kernel
ms.assetid: c40b99be-5627-44f3-9853-c3ae31a8035c
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtCreateFile, ZwCreateFile, ZwCreateFile routine [Kernel-Mode Driver Architecture], k111_80b1882a-8617-45d4-a783-dbc3bfc9aad4.xml, kernel.zwcreatefile, wdm/NtCreateFile, wdm/ZwCreateFile
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
-	ZwCreateFile
-	NtCreateFile
product: Windows
targetos: Windows
req.typenames: 
---

# NtCreateFile function


## -description


The <b>ZwCreateFile</b> routine creates a new file or opens an existing file.


## -parameters




### -param FileHandle [out]

A pointer to a HANDLE variable that receives a handle to the file.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects, the caller can specify any of the following access rights, which are specific to files.

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Allows caller to do this</th>
</tr>
<tr>
<td>
FILE_READ_DATA

</td>
<td>
Read data from the file.

</td>
</tr>
<tr>
<td>
FILE_READ_ATTRIBUTES

</td>
<td>
Read the attributes of the file. (For more information, see the description of the <i>FileAttributes</i> parameter.)

</td>
</tr>
<tr>
<td>
FILE_READ_EA

</td>
<td>
Read the extended attributes (EAs) of the file. This flag is irrelevant for device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_WRITE_DATA

</td>
<td>
Write data to the file.

</td>
</tr>
<tr>
<td>
FILE_WRITE_ATTRIBUTES

</td>
<td>
Write the attributes of the file. (For more information, see the description of the <i>FileAttributes</i> parameter.)

</td>
</tr>
<tr>
<td>
FILE_WRITE_EA 

</td>
<td>
Change the extended attributes (EAs) of the file. This flag is irrelevant for device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_APPEND_DATA

</td>
<td>
Append data to the file.

</td>
</tr>
<tr>
<td>
FILE_EXECUTE

</td>
<td>
Use system paging I/O to read data from the file into memory. This flag is irrelevant for device and intermediate drivers.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>    Do not specify FILE_READ_DATA, FILE_WRITE_DATA, FILE_APPEND_DATA, or FILE_EXECUTE when you create or open a directory.</div>
<div> </div>
The caller can only specify a generic access right, GENERIC_<i>XXX</i>, for a file, not a directory. Generic access rights correspond to specific access rights as shown in the following table.

<table>
<tr>
<th>Generic access right</th>
<th>Set of specific access rights</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES,  FILE_READ_EA, and SYNCHRONIZE.

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE.

</td>
</tr>
<tr>
<td>
GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, FILE_EXECUTE, FILE_READ_ATTRIBUTES, and SYNCHRONIZE. This value is irrelevant for device and intermediate drivers.

</td>
</tr>
<tr>
<td>
GENERIC_ALL

</td>
<td>
FILE_ALL_ACCESS.

</td>
</tr>
</table>
 

For example, if you specify GENERIC_READ for a file object, the routine maps this value to the FILE_GENERIC_READ bitmask of specific access rights. In the preceding table, the specific access rights that are listed for GENERIC_READ correspond to the access flags that are contained in the FILE_GENERIC_READ bitmask.

If the file is actually a directory, the caller can also specify the following generic access rights.

<table>
<tr>
<th><i>DesiredAccess</i> flag</th>
<th>Allows caller to do this</th>
</tr>
<tr>
<td>
FILE_LIST_DIRECTORY

</td>
<td>
List the files in the directory.

</td>
</tr>
<tr>
<td>
FILE_TRAVERSE

</td>
<td>
Traverse the directory, in other words, include the directory in the path of a file.

</td>
</tr>
</table>
 

For more information about access rights, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.


### -param ObjectAttributes [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


### -param IoStatusBlock [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that receives the final completion status and other information about the requested operation. In particular, the <b>Information</b> member receives one of the following values:

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

A pointer to a LARGE_INTEGER that contains the initial allocation size, in bytes, for a file that is created or overwritten. If <i>AllocationSize</i> is <b>NULL</b>, no allocation size is specified. If no file is created or overwritten, <i>AllocationSize</i> is ignored.


### -param FileAttributes [in]

Specifies one or more FILE_ATTRIBUTE_<i>XXX</i> flags, which represent the file attributes to set if you create or overwrite a file. The caller usually specifies FILE_ATTRIBUTE_NORMAL, which sets the default attributes. For a list of valid FILE_ATTRIBUTE_<i>XXX</i> flags, see the <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> routine in the Microsoft Windows SDK documentation. If no file is created or overwritten, <i>FileAttributes</i> is ignored.


### -param ShareAccess [in]

Type of share access, which is specified as zero or any combination of the following flags.

<table>
<tr>
<th><i>ShareAccess</i> flag</th>
<th>Allows other threads to do this</th>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
Read the file

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
Write the file

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
Delete the file

</td>
</tr>
</table>
 

Device and intermediate drivers usually set <i>ShareAccess</i> to zero, which gives the caller exclusive access to the open file.


### -param CreateDisposition [in]

Specifies the action to perform if the file does or does not exist. <i>CreateDisposition</i> can be one of the values in the following table.

<table>
<tr>
<th><i>CreateDisposition</i> value</th>
<th>Action if file exists</th>
<th>Action if file does not exist</th>
</tr>
<tr>
<td>
FILE_SUPERSEDE

</td>
<td>
Replace the file.

</td>
<td>
Create the file.

</td>
</tr>
<tr>
<td>
FILE_CREATE

</td>
<td>
Return an error.

</td>
<td>
Create the file.

</td>
</tr>
<tr>
<td>
FILE_OPEN

</td>
<td>
Open the file.

</td>
<td>
Return an error.

</td>
</tr>
<tr>
<td>
FILE_OPEN_IF

</td>
<td>
Open the file.

</td>
<td>
Create the file.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE

</td>
<td>
Open the file, and overwrite it.

</td>
<td>
Return an error.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE_IF

</td>
<td>
Open the file, and overwrite it.

</td>
<td>
Create the file.

</td>
</tr>
</table>
 


### -param CreateOptions [in]

Specifies the options to apply when the driver creates or opens the file. Use one or more of the flags in the following table.

<table>
<tr>
<th><i>CreateOptions</i> flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_DIRECTORY_FILE

</td>
<td>
The file is a directory. Compatible <i>CreateOptions</i> flags are FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. The <i>CreateDisposition</i> parameter must be set to FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF.

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file is <u>not</u> a directory. The file object to open can represent a data file; a logical, virtual, or physical device; or a volume.

</td>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, file-system drivers, and drivers that write data to the file must actually transfer the data to the file before any requested write operation is considered complete.

</td>
</tr>
<tr>
<td>
FILE_SEQUENTIAL_ONLY

</td>
<td>
All access to the file will be sequential.

</td>
</tr>
<tr>
<td>
FILE_RANDOM_ACCESS

</td>
<td>
Access to the file can be random, so no sequential read-ahead operations should be performed by file-system drivers or by the system.

</td>
</tr>
<tr>
<td>
FILE_NO_INTERMEDIATE_BUFFERING

</td>
<td>
The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the <i>DesiredAccess</i> parameter's FILE_APPEND_DATA flag.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file-position pointer. If this flag is set, the SYNCHRONIZE flag must be set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the file are performed synchronously. Waits in the system that synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file-position context. If this flag is set, the SYNCHRONIZE flag must be set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
FILE_CREATE_TREE_CONNECTION

</td>
<td>
Create a tree connection for this file in order to open it over the network. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_COMPLETE_IF_OPLOCKED

</td>
<td>
Complete this operation immediately with an alternate success code of STATUS_OPLOCK_BREAK_IN_PROGRESS if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file. This flag is not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_NO_EA_KNOWLEDGE

</td>
<td>
If the extended attributes (EAs) for an existing file being opened indicate that the caller must understand EAs to properly interpret the file, <b>ZwCreateFile</b> should return an error. This flag is irrelevant for device and intermediate drivers.

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
The system deletes the file when the last handle to the file is passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>. If this flag is set, the DELETE flag must be set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
FILE_OPEN_BY_FILE_ID

</td>
<td>
The file name that is specified by the <i>ObjectAttributes</i> parameter includes a binary 8-byte or 16-byte file reference number or object ID for the file, depending on the file system as shown below. Optionally, a device name followed by a backslash character may proceed these binary values. For example, a device name will have the following format.

<pre class="syntax">\??\C:\&lt;8 bytes of binary FileID&gt;
\device\HardDiskVolume1\&lt;16 bytes of binary ObjectID&gt;</pre>

<ul>
<li>
On NTFS, this can be a 8-byte or 16-byte reference number or object ID. A 16-byte reference number is the same as an 8-byte number padded with zeros.

</li>
<li>
On ReFS, this can be an 8-byte or 16-byte reference number. A 16-byte number is not related to an 8-byte number. Object IDs are not supported.

</li>
<li>
The FAT, ExFAT, UDFS, and CDFS file systems do not support this flag.

</li>
</ul>


This number is assigned by and specific to the particular file system.

<div class="alert"><b>Note</b>  Because the filename field will partly contain a binary blob, it is incorrect to assume that this is a valid Unicode string, and more importantly may not be a null terminated string.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_OPEN_FOR_BACKUP_INTENT

</td>
<td>
The file is being opened for backup intent. Therefore, the system should check for certain access rights and grant the caller the appropriate access to the file—before checking the <i>DesiredAccess</i> parameter against the file's security descriptor. This flag not used by device and intermediate drivers.

</td>
</tr>
<tr>
<td>
FILE_RESERVE_OPFILTER

</td>
<td>
This flag allows an application to request a Filter opportunistic lock (oplock) to prevent other applications from getting share violations. If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED. For more information, see the following Remarks section.

</td>
</tr>
<tr>
<td>
FILE_OPEN_REQUIRING_OPLOCK

</td>
<td>
The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and will fail the create with a return code of STATUS_CANNOT_BREAK_OPLOCK if the result would be to break an existing oplock.

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_SESSION_AWARE

</td>
<td>
The client opening the file or device is session aware and per session access is validated if necessary.

<div class="alert"><b>Note</b>    The FILE_SESSION_AWARE flag is available starting withWindows 8.</div>
<div> </div>
</td>
</tr>
</table>
 


### -param EaBuffer [in, optional]

For device and intermediate drivers, this parameter must be a <b>NULL</b> pointer.


### -param EaLength [in]

For device and intermediate drivers, this parameter must be zero.


## -returns



<b>ZwCreateFile</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS error code on failure. In the latter case, the caller can determine the cause of the failure by checking the <i>IoStatusBlock</i> parameter.

<div class="alert"><b>Note</b>  <b>ZwCreateFile</b> might return STATUS_FILE_LOCK_CONFLICT as the return value or in the <b>Status</b> member of the <b>IO_STATUS_BLOCK</b> structure that is pointed to by the <i>IoStatusBlock</i> parameter. This would occur only if the NTFS log file is full, and an error occurs while <b>ZwCreateFile</b> tries to handle this situation.</div>
<div> </div>



## -remarks



<b>ZwCreateFile</b> supplies a handle that the caller can use to manipulate a file's data, or the file object's state and attributes. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Once the handle pointed to by <i>FileHandle</i> is no longer in use, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

There are two alternate ways to specify the name of the file to be created or opened with <b>ZwCreateFile</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes.</i>

</li>
<li>
As pathname relative to the directory file represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>.

</li>
</ol>
Setting certain flags in the <i>DesiredAccess</i> parameter results in the following effects:

<ul>
<li>
For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i>, the SYNCHRONIZE flag must be set. Otherwise, a caller that is a device or intermediate driver must synchronize an I/O completion by using an event object.

</li>
<li>
If the caller sets only the FILE_APPEND_DATA and SYNCHRONIZE flags, it can write only to the end of the file, and any offset information about write operations to the file is ignored. The file will automatically be extended as necessary for this type of operation.

</li>
<li>
Setting the FILE_WRITE_DATA flag for a file also allows the caller to write beyond the end of the file. Again, the file is automatically extended as necessary.

</li>
<li>
If the caller sets only the FILE_EXECUTE and SYNCHRONIZE flags, it cannot directly read or write any data to the file using the returned <i>FileHandle</i>. That is, all operations on the file occur through the system pager in response to instruction and data-access operations. Device and intermediate drivers should not set the FILE_EXECUTE flag.

</li>
</ul>
The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both callers have the appropriate access privileges, the file can be successfully opened and shared. If the original caller of <b>ZwCreateFile</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other caller can open the file—that is, the original caller is granted exclusive access.

To successfully open a shared file, the <i>DesiredAccess</i> flags must be compatible with the <i>DesiredAccess</i> and <i>ShareAccess</i> flags of all the previous open operations that have not yet been released through . That is, the <i>DesiredAccess</i> specified to <b>ZwCreateFile</b> for a given file must not conflict with the accesses that other openers of the file have disallowed.

The <i>CreateDisposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to <b>ZwCreateFile</b> with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that, if the file has already been opened by another thread, it opened the file by specifying a <i>ShareAccess</i> parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The <i>CreateDisposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>ZwCreateFile</b> is called with a existing file and either of these <i>CreateDisposition</i> values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

<ul>
<li>
The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i>.

</li>
<li>
The specified file attributes are logically ORed with those already on the file. This implies that, if the file has already been opened by another thread, a subsequent caller of <b>ZwCreateFile</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Microsoft Windows 3.1, and OS/2.

</li>
</ul>
The FILE_DIRECTORY_FILE <i>CreateOptions</i> value specifies that the file to be created or opened is a directory. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent <i>CreateOptions</i> or <i>CreateDisposition</i> value, the call to <b>ZwCreateFile</b> will fail.

The FILE_NO_INTERMEDIATE_BUFFERING <i>CreateOptions</i> flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this flag places the following restrictions on the caller's parameters to other <b>Zw<i>Xxx</i>File</b> routines.

<ul>
<li>
Any optional <i>ByteOffset</i> passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a> must be a multiple of the sector size.

</li>
<li>
The <i>Length</i> passed to <b>ZwReadFile</b> or <b>ZwWriteFile</b> must be an integral of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

</li>
<li>
Buffers must be aligned in accordance with the alignment requirement of the underlying device. To obtain this information, call <b>ZwCreateFile</b> to get a handle for the file object that represents the physical device, and pass that handle to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>. For a list of the system's FILE_<i>XXX</i>_ALIGNMENT values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.

</li>
<li>
Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is a multiple of the sector size.

</li>
</ul>
The FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT <i>CreateOptions</i> flags, which are mutually exclusive as their names suggest, specify that all I/O operations on the file will be synchronous—as long as they occur through the file object referred to by the returned <i>FileHandle</i>. All I/O on such a file is serialized across all threads using the returned handle. If either of these <i>CreateOptions</i> flags is set, the SYNCHRONIZE <i>DesiredAccess</i> flag must also be set—to compel the I/O manager to use the file object as a synchronization object. In these cases, the I/O manager keeps track of the current file-position offset, which you can pass to <b>ZwReadFile</b> and <b>ZwWriteFile</b>. Call <b>ZwQueryInformationFile</b> or <b>ZwSetInformationFile</b> to get or set this position.

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is <u>not</u> specified and <b>ZwCreateFile</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file. If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does <u>not</u> occur and <b>ZwCreateFile</b> attempts to directly open the reparse point file. In either case, if the open operation was successful, <b>ZwCreateFile</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>ZwCreateFile</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially allow a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>ZwCreateFile</b> and then request any oplock. This ensures that an oplock owner will be notified of any subsequent open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

An application that uses the FILE_OPEN_REQUIRING_OPLOCK flag must request an oplock after this call succeeds, or all subsequent attempts to open the file will be blocked without the benefit of normal oplock processing. Similarly, if this call succeeds but the subsequent oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

<div class="alert"><b>Note</b>  The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.</div>
<div> </div>
The <i>CreateOptions</i> flag FILE_RESERVE_OPFILTER allows an application to request a Level 1, Batch, or Filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for Filter oplocks. To use it, you must complete the following steps:

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
Step three makes this practical only for Filter oplocks. The handle opened in step 3 can have a <i>DesiredAccess</i> that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a Filter oplock. However, any <i>DesiredAccess</i> greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a Level 1 or Batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

Callers of <b>ZwCreateFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateFile</b>" instead of "<b>ZwCreateFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a>
 

 

