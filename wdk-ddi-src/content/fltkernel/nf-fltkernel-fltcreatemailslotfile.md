---
UID: NF:fltkernel.FltCreateMailslotFile
title: FltCreateMailslotFile function (fltkernel.h)
description: Minifilter drivers call FltCreateMailslotFile to create a new pipe or open an existing mailslot.
old-location: ifsk\fltcreatemailslotfile.htm
tech.root: ifsk
ms.assetid: A727CDC1-A17A-4ABE-92AC-7CAEC11B78D1
ms.date: 04/16/2018
ms.keywords: FltCreateMailslotFile, FltCreateMailslotFile function [Installable File System Drivers], fltkernel/FltCreateMailslotFile, ifsk.fltcreatemailslotfile
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8.
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Fltmgr.lib
- Fltmgr.dll
api_name:
- FltCreateMailslotFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCreateMailslotFile function


## -description


Minifilter drivers call <b>FltCreateMailslotFile</b> to create a new pipe or open an existing mailslot.


## -parameters




### -param Filter [in]

An opaque filter pointer for the caller. 


### -param Instance [in, optional]

An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume for the mailslot file system. This parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request is sent to the device object at the top of the file system driver stack for the volume. If it is non-<b>NULL</b>, the request is sent only to minifilter driver instances that are attached below the specified instance. 


### -param FileHandle [out]

A pointer to a caller-allocated variable that receives the file handle if the call to  <b>FltCreateMailslotFile</b> is successful. 


### -param FileObject [out, optional]

A pointer to a caller-allocated variable that receives the file object pointer if the call to <b>FltCreateMailslotFile</b> is successful. This parameter is optional and can be <b>NULL</b>. 


### -param DesiredAccess [in]

A bitmask of flags that specify the type of access that the caller requires to the file or directory. The set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for file objects. 

<table>
<tr>
<th>DesiredAccess Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_READ_DATA

</td>
<td>
Data can be read from the named mailslot.

</td>
</tr>
<tr>
<td>
FILE_READ_ATTRIBUTES

</td>
<td>
<i>FileAttributes</i> flags can be read.  For additional information, see the table of valid flag values in the <i>FileAttributes</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>.

</td>
</tr>
<tr>
<td>
READ_CONTROL

</td>
<td>
The access control list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">ACL</a>) and ownership information associated with the mailslot can be read.

</td>
</tr>
<tr>
<td>
FILE_WRITE_DATA

</td>
<td>
Data can be written to the mailslot.

</td>
</tr>
<tr>
<td>
FILE_WRITE_ATTRIBUTES

</td>
<td>
<i>FileAttributes</i> flags can be written.

</td>
</tr>
<tr>
<td>
FILE_APPEND_DATA

</td>
<td>
Data can be appended to the mailslot.

</td>
</tr>
<tr>
<td>
WRITE_DAC 

</td>
<td>
The discretionary access control list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">DACL</a>) associated with the mailslot can be written.

</td>
</tr>
<tr>
<td>
WRITE_OWNER 

</td>
<td>
Ownership information associated with the mailslot can be written.

</td>
</tr>
<tr>
<td>
ACCESS_SYSTEM_SECURITY

</td>
<td>
The caller will have write access to the mailslot's SACL

</td>
</tr>
<tr>
<td>
SYNCHRONIZE

</td>
<td>
The caller can synchronize the completion of an I/O operation by waiting for the returned <i>FileHandle</i> to be set to the Signaled state. This flag must be set if the <i>CreateOptions</i> FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag is set. 

</td>
</tr>
</table>
 

Alternatively, for any file object that does not represent a directory, you can specify one or more of the following generic <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> flags. (The STANDARD_RIGHTS_<i>XXX</i> flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table. 

<table>
<tr>
<th>DesiredAccess to File Values</th>
<th>Maps to <i>DesiredAccess</i> Flags</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, FILE_READ_DATA, and SYNCHRONIZE. 

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_APPEND_DATA, and SYNCHRONIZE. 

</td>
</tr>
</table>
 


### -param ObjectAttributes [in]

A pointer to an opaque <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that is already initialized with <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>. If the caller is running in the system process context, this parameter can be <b>NULL</b>. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to <b>InitializeObjectAttributes</b>. Members of this structure for a file object are listed in the following table. 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONG </b><b>Length</b>

</td>
<td>
The number of bytes of data that are contained in the structure pointed to by <i>ObjectAttributes</i>. This value must be at least <b>sizeof</b>(OBJECT_ATTRIBUTES).

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING </b><b>ObjectName</b>

</td>
<td>
A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the mailslot to be created or opened. This name must be a fully qualified file specification or the name of a device object unless it is the name of a file relative to the directory specified by <b>RootDirectory</b>. For example, "\Device\Mailslot\myslot" or "\??\mailslot\myslot" could both be valid file specifications. (Note: "\??" replaces "\DosDevices" as the name of the Win32 object namespace. "\DosDevices" still works, but "\??" is translated faster by the object manager.)

</td>
</tr>
<tr>
<td>
<b>HANDLE </b><b>RootDirectory</b>

</td>
<td>
An optional handle to a directory, obtained by a preceding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>. If this value is <b>NULL</b>, the <i>ObjectName</i>member must be a fully qualified file specification that includes the full path to the target mailslot. If this value is non-<b>NULL</b>, the <i>ObjectName</i> member specifies a mailslot name that is relative to this directory.

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR </b><b>SecurityDescriptor</b>

</td>
<td>
An optional security descriptor (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a>) to be applied to a mailslot. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl">ACLs</a> specified by such a security descriptor are only applied to the mailslot when it is created. If the value is <b>NULL</b> when a mailslot is created, the ACL placed on the mailslot is dependant on the mailslot file system and may allow a client with any access to create an instance.

</td>
</tr>
<tr>
<td>
<b>ULONG </b><b>Attributes</b>

</td>
<td>
A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <i>ObjectName</i> rather than performing an exact-match search. 

</td>
</tr>
</table>
 


### -param IoStatusBlock [out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. On return from <b>FltCreateMailslotFile</b>, the <b>Information</b> member of the variable contains one of the following values:

FILE_CREATED

FILE_OPENED


### -param CreateOptions [in]

The options to be applied when creating or opening the mailslot, as a compatible combination of the following flags. 

<table>
<tr>
<th><i>CreateOptions</i> flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, file systems, and drivers that write data to the mailslot must actually transfer the data into the mailslot before any requested write operation is considered complete. This flag is automatically set if the <i>CreateOptions</i> flag FILE_NO_INTERMEDIATE_BUFFERING is set.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the mailslot are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the mailslot position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. 

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the mailslot are performed synchronously. Waits in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object.

</td>
</tr>
</table>
 


### -param MailslotQuota [in]

The size, in bytes, of the buffer for writes to the mailslot.


### -param MaximumMessageSize [in]

The maximum size, in bytes, of a message to write to the mailslot. A message of any size is specified by the value 0.


### -param ReadTimeout [in]

The time a read operation waits for a message to be available in the mailslot. The default timeout is expressed in 100-nanosecond increments as a negative integer. For example, 250 milliseconds is specified as –10 * 1000 * 250. Additionally, the following values have special meanings.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Returns immediately if no message is present.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>-1</dt>
</dl>
</td>
<td width="60%">
Waits forever for a message.

</td>
</tr>
</table>
 


### -param DriverContext [in, optional]

Optional pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_io_driver_create_context">IO_DRIVER_CREATE_CONTEXT</a> structure already initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioinitializedrivercreatecontext">IoInitializeDriverCreateContext</a>.


## -returns



<b>FltCreateMailslotFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The filter or instance specified in the <i>Filter</i> or <i>Instance</i> parameters is being torn down. This status code can be received if the open request crosses a volume mount point and the <i>Instance</i> parameter is non-<b>NULL</b>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This error code indicates incorrect syntax for the object path. 

</td>
</tr>
</table>
 




## -remarks



The <b>FltCreateMailslotFile</b> function allows minifilter drivers to create or open mailslot instances. This is useful for creating virtual mailslots or for creating a mailslot group that distributes to several other mailslots.

The <i>instance</i> parameter is either <b>NULL</b> or is previously set by attaching to the mailslot volume. A volume pointer is obtained by passing "\Device\Mailslot" as the volume name to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumefromname">FltGetVolumeFromName</a>.

To specify an extra create parameter (ECP) as part of a create operation, initialize the <b>ExtraCreateParameter</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_io_driver_create_context">IO_DRIVER_CREATE_CONTEXT</a> structure with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a> routine.  If ECPs are used, they must be allocated, initialized, and freed using their associated support routines.  Upon returning from the call of <b>FltCreateMailslotFile</b>, the ECP list is unchanged and may be passed to additional calls of <b>FltCreateMailslotFile</b> for other create operations.  The ECP list structure is not automatically deallocated. The caller of <b>FltCreateMailslotFile</b> must deallocate this structure by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a> routine.


     If <i>Instance</i> is not <b>NULL</b>, the create request from <b>FltCreateMailslotFile</b> is sent only to the instances attached below the specified minifilter driver instance and to the mailslot file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the mailslot file system.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist">FltAllocateExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist">FltFreeExtraCreateParameterList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_io_driver_create_context">IO_DRIVER_CREATE_CONTEXT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-ioinitializedrivercreatecontext">IoInitializeDriverCreateContext</a>
 

 

