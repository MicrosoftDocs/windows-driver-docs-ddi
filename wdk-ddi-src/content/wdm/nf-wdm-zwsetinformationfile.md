---
UID: NF:wdm.ZwSetInformationFile
title: ZwSetInformationFile function
author: windows-driver-content
description: The ZwSetInformationFile routine changes various kinds of information about a file object.
old-location: kernel\zwsetinformationfile.htm
old-project: kernel
ms.assetid: a6f92495-89f0-4728-b6d8-083c55bc3206
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, I, NtSetInformationFile, S, Z, ZwSetInformationFile, ZwSetInformationFile routine [Kernel-Mode Driver Architecture], a, e, f, i, k111_91ac021a-37b3-4d2d-9369-c80659e0dcd7.xml, kernel.zwsetinformationfile, l, m, n, o, r, t, w, wdm/NtSetInformationFile, wdm/ZwSetInformationFile"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwSetInformationFile
-	NtSetInformationFile
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwSetInformationFile function


## -description


The <b>ZwSetInformationFile</b> routine changes various kinds of information about a file object.


## -syntax


````
NTSTATUS ZwSetInformationFile(
  _In_  HANDLE                 FileHandle,
  _Out_ PIO_STATUS_BLOCK       IoStatusBlock,
  _In_  PVOID                  FileInformation,
  _In_  ULONG                  Length,
  _In_  FILE_INFORMATION_CLASS FileInformationClass
);
````


## -parameters




### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>.


### -param IoStatusBlock [out]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. The <b>Information</b> member receives the number of bytes set on the file.


### -param FileInformation [in]

Pointer to a buffer that contains the information to set for the file. The particular structure in this buffer is determined by the <i>FileInformationClass</i> parameter. Setting any member of the structure to zero tells <b>ZwSetInformationFile</b> to leave the current information about the file for that member unchanged.


### -param Length [in]

The size, in bytes, of the <i>FileInformation</i> buffer.


### -param FileInformationClass [in]

The type of information, supplied in the buffer pointed to by <i>FileInformation</i>, to set for the file. Device and intermediate drivers can specify any of the following <a href="..\wdm\ne-wdm-_file_information_class.md">FILE_INFORMATION_CLASS</a> values.

<table>
<tr>
<th><i>FileInformationClass</i> Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
Change the information that is supplied in a <a href="..\wdm\ns-wdm-_file_basic_information.md">FILE_BASIC_INFORMATION</a> structure. The caller must have opened the file with the FILE_WRITE_ATTRIBUTES flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileDispositionInformation</b>

</td>
<td>
Usually, sets the <b>DeleteFile</b> member of a <a href="..\ntddk\ns-ntddk-_file_disposition_information.md">FILE_DISPOSITION_INFORMATION</a> to <b>TRUE</b>, so the file can be deleted when <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> is called to release the last open handle to the file object. The caller must have opened the file with the DELETE flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileEndOfFileInformation</b>

</td>
<td>
Change the current end-of-file information, supplied in a <a href="..\ntddk\ns-ntddk-_file_end_of_file_information.md">FILE_END_OF_FILE_INFORMATION</a> structure. The operation can either truncate or extend the file. The caller must have opened the file with the FILE_WRITE_DATA flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileIoPriorityHintInformation</b>

</td>
<td>
Change the current default IRP priority hint for the file handle. The new value is supplied in a <a href="..\wdm\ns-wdm-_file_io_priority_hint_information.md">FILE_IO_PRIORITY_HINT_INFORMATION</a> structure.

<div class="alert"><b>Note</b>    This structure must be 8-byte aligned.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
<b>FileLinkInformation</b>

</td>
<td>
Create a hard link to an existing file, which is specified in a <a href="..\ntifs\ns-ntifs-_file_link_information.md">FILE_LINK_INFORMATION</a> structure. Not all file systems support hard links; for example NTFS does while FAT does not.

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Change the current file information, which is stored in a <a href="..\wdm\ns-wdm-_file_position_information.md">FILE_POSITION_INFORMATION</a> structure.

</td>
</tr>
<tr>
<td>
<b>FileRenameInformation</b>

</td>
<td>
Change the current file name, which is supplied in a <a href="..\ntifs\ns-ntifs-_file_rename_information.md">FILE_RENAME_INFORMATION</a> structure. The caller must have DELETE access to the file.

</td>
</tr>
<tr>
<td>
<b>FileShortNameInformation</b>

</td>
<td>
Change the current short file name, which is supplied in a <a href="..\ntddk\ns-ntddk-_file_name_information.md">FILE_NAME_INFORMATION</a> structure. The file must be on an NTFS volume, and the caller must have opened the file with the <i>DesiredAccess</i> DELETE flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileValidDataLengthInformation</b>

</td>
<td>
Change the current valid data length for the file, which is supplied in a <a href="..\ntddk\ns-ntddk-_file_valid_data_length_information.md">FILE_VALID_DATA_LENGTH_INFORMATION</a> structure. The file must be on an NTFS volume, and the caller must have opened the file with the FILE_WRITE_DATA flag set in the <i>DesiredAccess</i> parameter. Non-administrators and remote users must have the <b>SeManageVolumePrivilege</b> privilege.

</td>
</tr>
<tr>
<td>
<b>FileReplaceCompletionInformation</b>

</td>
<td>
Change or remove the I/O completion port for the specified file handle. The caller supplies a pointer to a <a href="..\ntifs\ns-ntifs-_file_completion_information.md">FILE_COMPLETION_INFORMATION</a> structure that specifies a port handle and a completion key. If the port handle is non-NULL, this handle specifies a new I/O completion port to associate with the file handle. To remove the I/O completion port associated with the file handle, set the port handle in the structure to NULL. To get a port handle, a user-mode caller can call the <a href="https://msdn.microsoft.com/40cb47fc-7b15-47f6-bee2-2611d4686053">CreateIoCompletionPort</a> function.

</td>
</tr>
</table>
 


## -returns



<b>ZwSetInformationFile</b> returns STATUS_SUCCESS or an appropriate error status.




## -remarks



<b>ZwSetInformationFile</b> changes information about a file. It ignores any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by a particular device or file system.

If you set <i>FileInformationClass</i> to <b>FileDispositionInformation</b>, you can subsequently pass <i>FileHandle</i> to <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> but not to any other <b>Zw<i>Xxx</i>File</b> routine. Because <b>FileDispositionInformation</b> causes the file to be marked for deletion, it is a programming error to attempt any subsequent operation on the handle other than closing it.

If you set <i>FileInformationClass</i> to <b>FilePositionInformation</b>, and the preceding call to <b>ZwCreateFile</b> included the FILE_NO_INTERMEDIATE_BUFFERING flag in the <i>CreateOptions</i> parameter, certain restrictions on the <b>CurrentByteOffset</b> member of the <a href="..\wdm\ns-wdm-_file_position_information.md">FILE_POSITION_INFORMATION</a> structure are enforced. For more information, see <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

If you set <i>FileInformationClass</i> to <b>FileEndOfFileInformation</b>, and the <b>EndOfFile</b> member of <a href="..\ntddk\ns-ntddk-_file_end_of_file_information.md">FILE_END_OF_FILE_INFORMATION</a> specifies an offset beyond the current end-of-file mark, <b>ZwSetInformationFile</b> extends the file and pads the extension with zeros.

For more information about working with files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Callers of <b>ZwSetInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtSetInformationFile</b>" instead of "<b>ZwSetInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\ntifs\ns-ntifs-_file_link_information.md">FILE_LINK_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="https://msdn.microsoft.com/40cb47fc-7b15-47f6-bee2-2611d4686053">CreateIoCompletionPort</a>



<a href="..\ntddk\ns-ntddk-_file_valid_data_length_information.md">FILE_VALID_DATA_LENGTH_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_end_of_file_information.md">FILE_END_OF_FILE_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\ntifs\ns-ntifs-_file_completion_information.md">FILE_COMPLETION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\ntddk\ns-ntddk-_file_name_information.md">FILE_NAME_INFORMATION</a>



<a href="..\wdm\ns-wdm-_file_basic_information.md">FILE_BASIC_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_file_disposition_information.md">FILE_DISPOSITION_INFORMATION</a>



<a href="..\wdm\ns-wdm-_file_io_priority_hint_information.md">FILE_IO_PRIORITY_HINT_INFORMATION</a>



<a href="..\wdm\ns-wdm-_file_position_information.md">FILE_POSITION_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_rename_information.md">FILE_RENAME_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

