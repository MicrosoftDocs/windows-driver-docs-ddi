---
UID: NF:ntifs.NtQueryInformationFile
title: NtQueryInformationFile function (ntifs.h)
description: The NtQueryInformationFile routine returns various kinds of information about a file object.
old-location: kernel\zwqueryinformationfile.htm
tech.root: kernel
ms.assetid: 007df07e-685b-4224-b9d6-55e87cf0bd5c
ms.date: 10/30/2019
ms.keywords: NtQueryInformationFile, ZwQueryInformationFile, ZwQueryInformationFile routine [Kernel-Mode Driver Architecture], k111_822ab812-a644-4574-8d89-c4ebf5b17ea5.xml, kernel.zwqueryinformationfile, wdm/NtQueryInformationFile, wdm/ZwQueryInformationFile
f1_keywords:
 - "ntifs/ZwQueryInformationFile"
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

# NtQueryInformationFile function

## -description

The **NtQueryInformationFile** routine returns various kinds of information about a file object. See also [**NtQueryInformationByName**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationbyname), which can be more efficiently used for a few file information classes.

## -parameters

### -param FileHandle [in]

Handle to a file object. The handle is created by a successful call to [**NtCreateFile**](nf-ntifs-ntcreatefile.md) or [**NtOpenFile**](nf-ntifs-ntopenfile.md), or to an equivalent file create or open routine.

### -param IoStatusBlock [out]

Pointer to an [IO_STATUS_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure that receives the final completion status and information about the operation. The **Information** member receives the number of bytes that this routine actually writes to the *FileInformation* buffer.

### -param FileInformation [out]

Pointer to a caller-allocated buffer into which the routine writes the requested information about the file object. The *FileInformationClass* parameter specifies the type of information that the caller requests.

### -param Length [in]

The size, in bytes, of the buffer pointed to by *FileInformation*.

### -param FileInformationClass [in]

Specifies the type of information to be returned about the file, in the buffer that *FileInformation* points to. Device and intermediate drivers can specify any of the following [FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) values.

| FILE_INFORMATION_CLASS value | Type of information returned |
| **FileAccessInformation** | A [FILE_ACCESS_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_access_information) structure. This structure contains an access mask. For more information about access masks, see [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask).
 |
 | **FileAlignmentInformation** | A [FILE_ALIGNMENT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information) structure. The caller can query this information as long as the file is open, without any particular requirements for *DesiredAccess*. This information is useful if the file was opened with the FILE_NO_INTERMEDIATE_BUFFERING flag specified in the *CreateOptions* parameter. |
 | **FileAllInformation** | A [FILE_ALL_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_all_information) structure. By combining several file-information structures into a single structure, **FILE_ALL_INFORMATION** reduces the number of queries required to obtain information about a file. |
 | **FileAttributeTagInformation** |
 | A [FILE_ATTRIBUTE_TAG_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_attribute_tag_information) structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the *DesiredAccess* parameter. |
 | **FileBasicInformation** | A [FILE_BASIC_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information) structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the *DesiredAccess* parameter. |
 | **FileCaseSensitiveInformation** | A [FILE_CASE_SENSITIVE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_case_sensitive_information) structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the *DesiredAccess* parameter. This value is available starting with Windows 10, version 1803. |
 | **FileCaseSensitiveInformationForceAccessCheck** | A [FILE_CASE_SENSITIVE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_case_sensitive_information) structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the *DesiredAccess* parameter. This is a special version of the FileCaseSensitiveInformation operation that is used to force the IOManager to perform access checks for the kernel-mode driver, similar to the checks that apply to a user-mode caller. This operation is only recognized by the IOManager and a file system should never receive it. This value is available starting with Windows 10, version 1803. |
 | **FileEaInformation** | A [FILE_EA_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_ea_information) structure. This structure specifies the size of the extended attributes block that is associated with the file. |
 | **FileInternalInformation** | A [FILE_INTERNAL_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_internal_information) structure. This structure specifies a 64-bit file ID that uniquely identifies a file in NTFS. On other file systems, this file ID is not guaranteed to be unique. |
 | **FileIoPriorityHintInformation** | A [FILE_IO_PRIORITY_HINT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_io_priority_hint_information) structure. The caller must have opened the file with the FILE_READ_DATA flag specified in the *DesiredAccess* parameter. |
 | **FileModeInformation** | A [FILE_MODE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_mode_information) structure. This structure contains a set of flags that specify the mode in which the file can be accessed. These flags are a subset of the options that can be specified in the *CreateOptions* parameter of the [**IoCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile) routine. |
 | **FileNameInformation** | A [FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information) structure. The structure can contain the file's full path or only a portion of it. The caller can query this information as long as the file is open, without any particular requirements for *DesiredAccess*. For more information about the file-name syntax, see the Remarks section later in this topic. |
 | **FileNetworkOpenInformation** | A [FILE_NETWORK_OPEN_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_network_open_information) structure. The caller must have opened the file with the FILE_READ_ATTRIBUTES flag specified in the *DesiredAccess* parameter. |
 | **FilePositionInformation** | A [FILE_POSITION_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information) structure. The caller must have opened the file with the *DesiredAccess* FILE_READ_DATA or FILE_WRITE_DATA flag specified in the *DesiredAccess* parameter, and with the FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag specified in the *CreateOptions* parameter. |
 | **FileStandardInformation** | A [FILE_STANDARD_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information) structure. The caller can query this information as long as the file is open, without any particular requirements for *DesiredAccess*. |
 | **FileIsRemoteDeviceInformation** | A [FILE_IS_REMOTE_DEVICE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_is_remote_device_information) structure. The caller can query this information as  long as the file is open, without any particular requirements for *DesiredAccess*. |

## -returns

**NtQueryInformationFile** returns STATUS_SUCCESS or an appropriate NTSTATUS error code.

## -remarks

**NtQueryInformationFile** returns information about the specified file object. Note that it returns zero in any member of a **FILE_*XXX*_INFORMATION** structure that is not supported by a particular device or file system.

When *FileInformationClass* = **FileNameInformation**, the file name is returned in the [FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information) structure. The precise syntax of the file name depends on a number of factors:

* If you opened the file by submitting a full path to [**NtCreateFile**](nf-ntifs-ntcreatefile.md), **NtQueryInformationFile** returns that full path.

* If the **ObjectAttributes->RootDirectory** handle was opened by name in a call to **NtCreateFile**, and subsequently the file was opened by **NtCreateFile** relative to this root-directory handle, **NtQueryInformationFile** returns the full path.

* If the **ObjectAttributes->RootDirectory** handle was opened by file ID (using the FILE_OPEN_BY_FILE_ID flag) in a call to **NtCreateFile**, and subsequently the file was opened by **NtCreateFile** relative to this root-directory handle, **NtQueryInformationFile** returns the relative path.

* However, if the user has **SeChangeNotifyPrivilege** (described in the Microsoft Windows SDK documentation), **NtQueryInformationFile** returns the full path in all cases.

* If only the relative path is returned, the file name string will not begin with a backslash.

* If the full path and file name are returned, the string will begin with a single backslash, regardless of its location. Thus the file C:\dir1\dir2\filename.ext will appear as \dir1\dir2\filename.ext, while the file \\server\share\dir1\dir2\filename.ext will appear as \server\share\dir1\dir2\filename.ext.

If **NtQueryInformationFile** fails because of a buffer overflow, drivers that implement **FileNameInformation** should return as many WCHAR characters of the file name as will fit in the buffer and specify the full length that is required in the *FileNameLength* parameter of the [FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information) structure. You should reissue the query by using the file name length so that you can retrieve the full file name. Drivers that do not follow this pattern might require a gradual increase in length until they retrieve the full file name. For more information about working with files, see [Using Files in a Driver](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-files-in-a-driver).

Callers of **NtQueryInformationFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
> If the call to this function occurs in user mode, you should use the name "**NtQueryInformationFile**" instead of "**ZwQueryInformationFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[FILE_ACCESS_INFORMATION](ns-ntifs-_file_access_information.md)

[FILE_ALIGNMENT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information)

[FILE_ALL_INFORMATION](ns-ntifs-_file_all_information.md)

[FILE_ATTRIBUTE_TAG_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_attribute_tag_information)

[FILE_BASIC_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information)

[FILE_EA_INFORMATION](ns-ntifs-_file_ea_information.md)

[FILE_INTERNAL_INFORMATION](ns-ntifs-_file_internal_information.md)

[FILE_IO_PRIORITY_HINT_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_io_priority_hint_information)

[FILE_IS_REMOTE_DEVICE_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_is_remote_device_information)

[FILE_MODE_INFORMATION](ns-ntifs-_file_mode_information.md)

[FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information)

[FILE_NETWORK_OPEN_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_network_open_information)

[FILE_POSITION_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information)

[FILE_STANDARD_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information)

[Using Nt and Zw Versions of the Native System Services Routines](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**NtCreateFile**](nf-ntifs-ntcreatefile.md)

[**NtQueryInformationByName**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationbyname)

[**NtSetInformationFile**](nf-ntifs-ntsetinformationfile.md)
