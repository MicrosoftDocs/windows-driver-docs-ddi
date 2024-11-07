---
UID: NF:wdm.ZwSetInformationFile
title: ZwSetInformationFile function (wdm.h)
description: The ZwSetInformationFile routine in wdm.h changes various kinds of information about a file object. It ignores unsupported members of FILE_XXX_INFORMATION.
tech.root: kernel
ms.date: 12/15/2022
author: lorihollasch
keywords: ["ZwSetInformationFile function"]
ms.keywords: NtSetInformationFile, ZwSetInformationFile, ZwSetInformationFile routine [Kernel-Mode Driver Architecture], k111_91ac021a-37b3-4d2d-9369-c80659e0dcd7.xml, kernel.zwsetinformationfile, wdm/NtSetInformationFile, wdm/ZwSetInformationFile
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwSetInformationFile
 - wdm/ZwSetInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwSetInformationFile
---

## -description

The **ZwSetInformationFile** routine changes various kinds of information about a file object.

## -parameters

### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md) or [ZwOpenFile](../ntifs/nf-ntifs-ntopenfile.md).

### -param IoStatusBlock [out]

Pointer to an [**IO_STATUS_BLOCK**](./ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the requested operation. The **Information** member receives the number of bytes set on the file.

### -param FileInformation [in]

Pointer to a buffer that contains the information to set for the file. The particular structure in this buffer is determined by the *FileInformationClass* parameter. For example, if the *FileInformationClass* parameter is set to the **FileDispositionInformationEx** constant, this parameter should be a pointer to a [**FILE_DISPOSITION_INFORMATION_EX**](../ntddk/ns-ntddk-_file_disposition_information_ex.md) structure.

### -param Length [in]

The size, in bytes, of the *FileInformation* buffer.

### -param FileInformationClass [in]

The type of information, supplied in the buffer pointed to by *FileInformation*, to set for the file. Device and intermediate drivers can specify any of the following [FILE_INFORMATION_CLASS](./ne-wdm-_file_information_class.md) values.

| *FileInformationClass* Value | Meaning |
|---|---|
| **FileBasicInformation** | Change the information that is supplied in a [**FILE_BASIC_INFORMATION**](./ns-wdm-_file_basic_information.md) structure. The caller must have opened the file with the FILE_WRITE_ATTRIBUTES flag set in the *DesiredAccess* parameter. |
| **FileDispositionInformation** | Request to delete the file when it is closed or cancel a previously requested deletion. The choice whether to delete or cancel is supplied in a [**FILE_DISPOSITION_INFORMATION**](../ntddk/ns-ntddk-_file_disposition_information.md) structure. The caller must have opened the file with the DELETE flag set in the *DesiredAccess* parameter. |
| **FileDispositionInformationEx** | Request to delete the file or cancel a previously requested deletion. The choice whether to delete or cancel, as well as settings for when and how the deletion should be performed, are supplied in a [**FILE_DISPOSITION_INFORMATION_EX**](../ntddk/ns-ntddk-_file_disposition_information_ex.md) structure. The caller must have opened the file with the DELETE\*\* flag set in the *DesiredAccess* parameter. |
| **FileEndOfFileInformation** | Change the current end-of-file information, supplied in a [**FILE_END_OF_FILE_INFORMATION**](../ntddk/ns-ntddk-_file_end_of_file_information.md) structure. The operation can either truncate or extend the file. The caller must have opened the file with the FILE_WRITE_DATA flag set in the *DesiredAccess* parameter. |
| **FileIoPriorityHintInformation** | Change the current default IRP priority hint for the file handle. The new value is supplied in a [**FILE_IO_PRIORITY_HINT_INFORMATION**](./ns-wdm-_file_io_priority_hint_information.md) structure. This structure must be 8-byte aligned. |
| **FileLinkInformation** | Create a hard link to an existing file, which is specified in a [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structure. Not all file systems support hard links; for example NTFS does while FAT does not. |
| **FilePositionInformation** | Change the current file information, which is stored in a [**FILE_POSITION_INFORMATION**](./ns-wdm-_file_position_information.md) structure. |
| **FileRenameInformation** | Change the current file name, which is supplied in a [**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md) structure. The caller must have DELETE access to the file. |
| **FileShortNameInformation** | Change the current short file name, which is supplied in a [**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md) structure. The file must be on an NTFS volume, and the caller must have opened the file with the *DesiredAccess* DELETE flag set in the *DesiredAccess* parameter. |
| **FileIoCompletionNotificationInformation** | Change the file IO completion notification flags. Supports the same flags as [SetFileCompletionNotificationModes](/windows/win32/api/winbase/nf-winbase-setfilecompletionnotificationmodes). |
| **FileValidDataLengthInformation** | Change the current valid data length for the file, which is supplied in a [**FILE_VALID_DATA_LENGTH_INFORMATION**](../ntddk/ns-ntddk-_file_valid_data_length_information.md) structure. The file must be on an NTFS volume, and the caller must have opened the file with the FILE_WRITE_DATA flag set in the *DesiredAccess* parameter. Non-administrators and remote users must have the **SeManageVolumePrivilege** privilege. |
| **FileReplaceCompletionInformation** | Change or remove the I/O completion port for the specified file handle. The caller supplies a pointer to a [**FILE_COMPLETION_INFORMATION**](../ntifs/ns-ntifs-_file_completion_information.md) structure that specifies a port handle and a completion key. If the port handle is non-NULL, this handle specifies a new I/O completion port to associate with the file handle. To remove the I/O completion port associated with the file handle, set the port handle in the structure to NULL. To get a port handle, a user-mode caller can call the [CreateIoCompletionPort](/windows/desktop/FileIO/createiocompletionport) function. |

## -returns

**ZwSetInformationFile** returns STATUS_SUCCESS or an appropriate error status.

## -remarks

**ZwSetInformationFile** changes information about a file. It ignores any member of a **FILE_*XXX*_INFORMATION** structure that is not supported by a particular device or file system.

If you set *FileInformationClass* to **FileDispositionInformation**, you can subsequently pass *FileHandle* to [ZwClose](../ntifs/nf-ntifs-ntclose.md) but not to any other **Zw*Xxx*File** routine. Because **FileDispositionInformation** causes the file to be marked for deletion, it is a programming error to attempt any subsequent operation on the handle other than closing it.

If you set *FileInformationClass* to **FilePositionInformation**, and the preceding call to **ZwCreateFile** included the FILE_NO_INTERMEDIATE_BUFFERING flag in the *CreateOptions* parameter, certain restrictions on the **CurrentByteOffset** member of the [**FILE_POSITION_INFORMATION**](./ns-wdm-_file_position_information.md) structure are enforced. For more information, see [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md).

If you set *FileInformationClass* to **FileEndOfFileInformation**, and the **EndOfFile** member of [**FILE_END_OF_FILE_INFORMATION**](../ntddk/ns-ntddk-_file_end_of_file_information.md) specifies an offset beyond the current end-of-file mark, **ZwSetInformationFile** extends the file and pads the extension with zeros.

For more information about working with files, see [Using Files in a Driver](/windows-hardware/drivers/kernel/using-files-in-a-driver).

Callers of **ZwSetInformationFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

If the call to this function occurs in user mode, you should use the name "**NtSetInformationFile**" instead of "**ZwSetInformationFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[CreateIoCompletionPort](/windows/desktop/FileIO/createiocompletionport)

[**FILE_BASIC_INFORMATION**](./ns-wdm-_file_basic_information.md)

[**FILE_COMPLETION_INFORMATION**](../ntifs/ns-ntifs-_file_completion_information.md)

[**FILE_DISPOSITION_INFORMATION**](../ntddk/ns-ntddk-_file_disposition_information.md)

[**FILE_END_OF_FILE_INFORMATION**](../ntddk/ns-ntddk-_file_end_of_file_information.md)

[**FILE_IO_PRIORITY_HINT_INFORMATION**](./ns-wdm-_file_io_priority_hint_information.md)

[**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md)

[**FILE_NAME_INFORMATION**](../ntddk/ns-ntddk-_file_name_information.md)

[**FILE_POSITION_INFORMATION**](./ns-wdm-_file_position_information.md)

[**FILE_RENAME_INFORMATION**](../ntifs/ns-ntifs-_file_rename_information.md)

[**FILE_VALID_DATA_LENGTH_INFORMATION**](../ntddk/ns-ntddk-_file_valid_data_length_information.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwClose](../ntifs/nf-ntifs-ntclose.md)

[ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)

[ZwOpenFile](../ntifs/nf-ntifs-ntopenfile.md)

[ZwQueryInformationFile](../ntifs/nf-ntifs-ntqueryinformationfile.md)
