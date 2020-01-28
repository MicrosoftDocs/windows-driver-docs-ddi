---
UID: NF:wdm.ZwQueryInformationFile
title: ZwQueryInformationFile function (wdm.h)
description: The ZwQueryInformationFile routine returns various kinds of information about a file object.
old-location: kernel\zwqueryinformationfile.htm
tech.root: kernel
ms.assetid: 007df07e-685b-4224-b9d6-55e87cf0bd5c
ms.date: 04/30/2018
ms.keywords: NtQueryInformationFile, ZwQueryInformationFile, ZwQueryInformationFile routine [Kernel-Mode Driver Architecture], k111_822ab812-a644-4574-8d89-c4ebf5b17ea5.xml, kernel.zwqueryinformationfile, wdm/NtQueryInformationFile, wdm/ZwQueryInformationFile
f1_keywords:
 - "wdm/ZwQueryInformationFile"
req.header: wdm.h
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwQueryInformationFile
- NtQueryInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryInformationFile function


## -description


The <b>ZwQueryInformationFile</b> routine returns various kinds of information about a file object.


## -parameters




### -param FileHandle [in]

Handle to a file object. The handle is created by a successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntopenfile">ZwOpenFile</a>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the operation. The <b>Information</b> member receives the number of bytes that this routine actually writes to the <i>FileInformation</i> buffer.


### -param FileInformation [out]

Pointer to a caller-allocated buffer into which the routine writes the requested information about the file object. The <i>FileInformationClass</i> parameter specifies the type of information that the caller requests.


### -param Length [in]

The size, in bytes, of the buffer pointed to by <i>FileInformation</i>.


### -param FileInformationClass [in]

Specifies the type of information to be returned about the file, in the buffer that <i>FileInformation</i> points to. Device and intermediate drivers can specify any of the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class">FILE_INFORMATION_CLASS</a> values.

<table>
<tr>
<th>FILE_INFORMATION_CLASS value</th>
<th>Type of information returned</th>
</tr>
<tr>
<td>
<b>FileAccessInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_access_information">FILE_ACCESS_INFORMATION</a> structure. This structure contains an access mask. For more information about access masks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>.

</td>
</tr>
<tr>
<td>
<b>FileAlignmentInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information">FILE_ALIGNMENT_INFORMATION</a> structure. The caller can query this information as long as the file is open, without any particular requirements for <i>DesiredAccess</i>. This information is useful if the file was opened with the FILE_NO_INTERMEDIATE_BUFFERING flag specified in the <i>CreateOptions</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileAllInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_all_information">FILE_ALL_INFORMATION</a> structure. By combining several file-information structures into a single structure, <b>FILE_ALL_INFORMATION</b> reduces the number of queries required to obtain information about a file.

</td>
</tr>
<tr>
<td>
<b>FileAttributeTagInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_attribute_tag_information">FILE_ATTRIBUTE_TAG_INFORMATION</a> structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a> structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileEaInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_ea_information">FILE_EA_INFORMATION</a> structure. This structure specifies the size of the extended attributes block that is associated with the file.

</td>
</tr>
<tr>
<td>
<b>FileInternalInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_internal_information">FILE_INTERNAL_INFORMATION</a> structure. This structure specifies a 64-bit file ID that uniquely identifies a file in NTFS. On other file systems, this file ID is not guaranteed to be unique.

</td>
</tr>
<tr>
<td>
<b>FileIoPriorityHintInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_io_priority_hint_information">FILE_IO_PRIORITY_HINT_INFORMATION</a> structure. The caller must have opened the file with the FILE_READ_DATA flag specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileModeInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_mode_information">FILE_MODE_INFORMATION</a> structure. This structure contains a set of flags that specify the mode in which the file can be accessed. These flags are a subset of the options that can be specified in the <i>CreateOptions</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile">IoCreateFile</a> routine.

</td>
</tr>
<tr>
<td>
<b>FileNameInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a> structure. The structure can contain the file's full path or only a portion of it. The caller can query this information as long as the file is open, without any particular requirements for <i>DesiredAccess</i>.

For more information about the file-name syntax, see the Remarks section later in this topic.

</td>
</tr>
<tr>
<td>
<b>FileNetworkOpenInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a> structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a> structure. The caller must have opened the file with the <i>DesiredAccess</i> FILE_READ_DATA or FILE_WRITE_DATA flag specified in the <i>DesiredAccess</i> parameter, and with the FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag specified in the <i>CreateOptions </i>parameter.

</td>
</tr>
<tr>
<td>
<b>FileStandardInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information">FILE_STANDARD_INFORMATION</a> structure. The caller can query this information as long as the file is open, without any particular requirements for <i>DesiredAccess</i>.

</td>
</tr>
<tr>
<td>
<b>FileIsRemoteDeviceInformation</b>

</td>
<td>
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_is_remote_device_information">FILE_IS_REMOTE_DEVICE_INFORMATION</a> structure. The caller can query this information as  long as the file is open, without any particular requirements for <i>DesiredAccess</i>.                         

</td>
</tr>
</table>
 


## -returns



<b>ZwQueryInformationFile </b>returns STATUS_SUCCESS or an appropriate NTSTATUS error code.




## -remarks



<b>ZwQueryInformationFile</b> returns information about the specified file object. Note that it returns zero in any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by a particular device or file system.

When <i>FileInformationClass</i> = <b>FileNameInformation</b>, the file name is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a> structure. The precise syntax of the file name depends on a number of factors:

<ul>
<li>
If you opened the file by submitting a full path to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>, <b>ZwQueryInformationFile</b> returns that full path.

</li>
<li>
If the <b>ObjectAttributes->RootDirectory</b> handle was opened by name in a call to <b>ZwCreateFile</b>, and subsequently the file was opened by <b>ZwCreateFile</b> relative to this root-directory handle, <b>ZwQueryInformationFile</b> returns the full path.

</li>
<li>
If the <b>ObjectAttributes->RootDirectory</b> handle was opened by file ID (using the FILE_OPEN_BY_FILE_ID flag) in a call to <b>ZwCreateFile</b>, and subsequently the file was opened by <b>ZwCreateFile</b> relative to this root-directory handle, <b>ZwQueryInformationFile</b> returns the relative path. 

</li>
<li>
However, if the user has <b>SeChangeNotifyPrivilege</b> (described in the Microsoft Windows SDK documentation), <b>ZwQueryInformationFile</b> returns the full path in all cases.

</li>
<li>
If only the relative path is returned, the file name string will not begin with a backslash.

</li>
<li>
If the full path and file name are returned, the string will begin with a single backslash, regardless of its location. Thus the file C:\dir1\dir2\filename.ext will appear as \dir1\dir2\filename.ext, while the file \\server\share\dir1\dir2\filename.ext will appear as \server\share\dir1\dir2\filename.ext.

</li>
</ul>
If <b>ZwQueryInformationFile</b> fails because of a buffer overflow, drivers that implement <b>FileNameInformation</b> should return as many WCHAR characters of the file name as will fit in the buffer and specify the full length that is required in the <i>FileNameLength</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a> structure. You should reissue the query by using the file name length so that you can retrieve the full file name. Drivers that do not follow this pattern might require a gradual increase in length until they retrieve the full file name. For more information about working with files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-files-in-a-driver">Using Files in a Driver</a>.

Callers of <b>ZwQueryInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtQueryInformationFile</b>" instead of "<b>ZwQueryInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_access_information">FILE_ACCESS_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information">FILE_ALIGNMENT_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_all_information">FILE_ALL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_attribute_tag_information">FILE_ATTRIBUTE_TAG_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_ea_information">FILE_EA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_internal_information">FILE_INTERNAL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_io_priority_hint_information">FILE_IO_PRIORITY_HINT_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_is_remote_device_information">FILE_IS_REMOTE_DEVICE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_mode_information">FILE_MODE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_network_open_information">FILE_NETWORK_OPEN_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information">FILE_STANDARD_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

