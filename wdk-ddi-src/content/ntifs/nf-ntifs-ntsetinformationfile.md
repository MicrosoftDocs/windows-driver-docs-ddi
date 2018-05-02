---
UID: NF:ntifs.NtSetInformationFile
title: NtSetInformationFile function
author: windows-driver-content
description: The ZwSetInformationFile routine changes various kinds of information about a file object.
old-location: kernel\zwsetinformationfile.htm
old-project: kernel
ms.assetid: a6f92495-89f0-4728-b6d8-083c55bc3206
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtSetInformationFile, ZwSetInformationFile, ZwSetInformationFile routine [Kernel-Mode Driver Architecture], k111_91ac021a-37b3-4d2d-9369-c80659e0dcd7.xml, kernel.zwsetinformationfile, wdm/NtSetInformationFile, wdm/ZwSetInformationFile
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
-	ZwSetInformationFile
-	NtSetInformationFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtSetInformationFile function


## -description


The <b>ZwSetInformationFile</b> routine changes various kinds of information about a file object.


## -parameters




### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. The <b>Information</b> member receives the number of bytes set on the file.


### -param FileInformation [in]

Pointer to a buffer that contains the information to set for the file. The particular structure in this buffer is determined by the <i>FileInformationClass</i> parameter. Setting any member of the structure to zero tells <b>ZwSetInformationFile</b> to leave the current information about the file for that member unchanged.


### -param Length [in]

The size, in bytes, of the <i>FileInformation</i> buffer.


### -param FileInformationClass [in]

The type of information, supplied in the buffer pointed to by <i>FileInformation</i>, to set for the file. Device and intermediate drivers can specify any of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff728840">FILE_INFORMATION_CLASS</a> values.

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
Change the information that is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545762">FILE_BASIC_INFORMATION</a> structure. The caller must have opened the file with the FILE_WRITE_ATTRIBUTES flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileDispositionInformation</b>

</td>
<td>
Usually, sets the <b>DeleteFile</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545765">FILE_DISPOSITION_INFORMATION</a> to <b>TRUE</b>, so the file can be deleted when <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> is called to release the last open handle to the file object. The caller must have opened the file with the DELETE flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileEndOfFileInformation</b>

</td>
<td>
Change the current end-of-file information, supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545780">FILE_END_OF_FILE_INFORMATION</a> structure. The operation can either truncate or extend the file. The caller must have opened the file with the FILE_WRITE_DATA flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileIoPriorityHintInformation</b>

</td>
<td>
Change the current default IRP priority hint for the file handle. The new value is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545802">FILE_IO_PRIORITY_HINT_INFORMATION</a> structure.

<div class="alert"><b>Note</b>    This structure must be 8-byte aligned.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
<b>FileLinkInformation</b>

</td>
<td>
Create a hard link to an existing file, which is specified in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540324">FILE_LINK_INFORMATION</a> structure. Not all file systems support hard links; for example NTFS does while FAT does not.

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Change the current file information, which is stored in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545848">FILE_POSITION_INFORMATION</a> structure.

</td>
</tr>
<tr>
<td>
<b>FileRenameInformation</b>

</td>
<td>
Change the current file name, which is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540344">FILE_RENAME_INFORMATION</a> structure. The caller must have DELETE access to the file.

</td>
</tr>
<tr>
<td>
<b>FileShortNameInformation</b>

</td>
<td>
Change the current short file name, which is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545817">FILE_NAME_INFORMATION</a> structure. The file must be on an NTFS volume, and the caller must have opened the file with the <i>DesiredAccess</i> DELETE flag set in the <i>DesiredAccess</i> parameter.

</td>
</tr>
<tr>
<td>
<b>FileValidDataLengthInformation</b>

</td>
<td>
Change the current valid data length for the file, which is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545873">FILE_VALID_DATA_LENGTH_INFORMATION</a> structure. The file must be on an NTFS volume, and the caller must have opened the file with the FILE_WRITE_DATA flag set in the <i>DesiredAccess</i> parameter. Non-administrators and remote users must have the <b>SeManageVolumePrivilege</b> privilege.

</td>
</tr>
<tr>
<td>
<b>FileReplaceCompletionInformation</b>

</td>
<td>
Change or remove the I/O completion port for the specified file handle. The caller supplies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn369252">FILE_COMPLETION_INFORMATION</a> structure that specifies a port handle and a completion key. If the port handle is non-NULL, this handle specifies a new I/O completion port to associate with the file handle. To remove the I/O completion port associated with the file handle, set the port handle in the structure to NULL. To get a port handle, a user-mode caller can call the <a href="https://msdn.microsoft.com/40cb47fc-7b15-47f6-bee2-2611d4686053">CreateIoCompletionPort</a> function.

</td>
</tr>
</table>
 


## -returns



<b>ZwSetInformationFile</b> returns STATUS_SUCCESS or an appropriate error status.




## -remarks



<b>ZwSetInformationFile</b> changes information about a file. It ignores any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by a particular device or file system.

If you set <i>FileInformationClass</i> to <b>FileDispositionInformation</b>, you can subsequently pass <i>FileHandle</i> to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> but not to any other <b>Zw<i>Xxx</i>File</b> routine. Because <b>FileDispositionInformation</b> causes the file to be marked for deletion, it is a programming error to attempt any subsequent operation on the handle other than closing it.

If you set <i>FileInformationClass</i> to <b>FilePositionInformation</b>, and the preceding call to <b>ZwCreateFile</b> included the FILE_NO_INTERMEDIATE_BUFFERING flag in the <i>CreateOptions</i> parameter, certain restrictions on the <b>CurrentByteOffset</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545848">FILE_POSITION_INFORMATION</a> structure are enforced. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>.

If you set <i>FileInformationClass</i> to <b>FileEndOfFileInformation</b>, and the <b>EndOfFile</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545780">FILE_END_OF_FILE_INFORMATION</a> specifies an offset beyond the current end-of-file mark, <b>ZwSetInformationFile</b> extends the file and pads the extension with zeros.

For more information about working with files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Callers of <b>ZwSetInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtSetInformationFile</b>" instead of "<b>ZwSetInformationFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/40cb47fc-7b15-47f6-bee2-2611d4686053">CreateIoCompletionPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545762">FILE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn369252">FILE_COMPLETION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545765">FILE_DISPOSITION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545780">FILE_END_OF_FILE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545802">FILE_IO_PRIORITY_HINT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540324">FILE_LINK_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545817">FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545848">FILE_POSITION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540344">FILE_RENAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545873">FILE_VALID_DATA_LENGTH_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
 

 

