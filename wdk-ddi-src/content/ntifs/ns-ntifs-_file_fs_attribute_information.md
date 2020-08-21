---
UID: NS:ntifs._FILE_FS_ATTRIBUTE_INFORMATION
title: _FILE_FS_ATTRIBUTE_INFORMATION (ntifs.h)
description: The FILE_FS_ATTRIBUTE_INFORMATION structure is used to query attribute information for a file system.
old-location: ifsk\file_fs_attribute_information.htm
tech.root: ifsk
ms.assetid: 373788d8-4963-4319-82ae-3a0675c9fff4
ms.date: 06/06/2019
keywords: ["FILE_FS_ATTRIBUTE_INFORMATION structure"]
ms.keywords: "*PFILE_FS_ATTRIBUTE_INFORMATION, FILE_FS_ATTRIBUTE_INFORMATION, FILE_FS_ATTRIBUTE_INFORMATION structure [Installable File System Drivers], PFILE_FS_ATTRIBUTE_INFORMATION, PFILE_FS_ATTRIBUTE_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_ATTRIBUTE_INFORMATION, fileinformationstructures_d3a65f15-7f98-492d-a65e-65db56c4c58d.xml, ifsk.file_fs_attribute_information, ntifs/FILE_FS_ATTRIBUTE_INFORMATION, ntifs/PFILE_FS_ATTRIBUTE_INFORMATION"
f1_keywords:
 - "ntifs/FILE_FS_ATTRIBUTE_INFORMATION"
 - "FILE_FS_ATTRIBUTE_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FILE_FS_ATTRIBUTE_INFORMATION
targetos: Windows
req.typenames: FILE_FS_ATTRIBUTE_INFORMATION, *PFILE_FS_ATTRIBUTE_INFORMATION
---

# _FILE_FS_ATTRIBUTE_INFORMATION structure

## -description

The **FILE_FS_ATTRIBUTE_INFORMATION** structure is used to query attribute information for a file system.

## -struct-fields

### -field FileSystemAttributes

Bitmask of flags specifying attributes of the specified file system, as a compatible combination of the following flags.

| Value | Meaning |
| ----- | ------- |
| **FILE_CASE_SENSITIVE_SEARCH** (0x00000001) | The file system supports case-sensitive file names. |
| **FILE_CASE_PRESERVED_NAMES** (0x00000002)| The file system preserves the case of file names when it places a name on disk. |
| **FILE_UNICODE_ON_DISK** (0x00000004) | The file system supports [Unicode](https://docs.microsoft.com/openspecs/windows_protocols/ms-smb/c7d64f17-1ab6-4151-b9e8-f15813235c83#gt_c305d0ab-8b94-461a-bd76-13b40cb8c4d8) in file names. |
| **FILE_PERSISTENT_ACLS** (0x00000008) | The file system preserves and enforces access control lists ([ACLs](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)). |
| **FILE_FILE_COMPRESSION** (0x00000010) | The file system supports file-based compression. This flag is incompatible with the **FILE_VOLUME_IS_COMPRESSED** flag. This flag does not affect how data is transferred over the network. |
| **FILE_VOLUME_QUOTAS** (0x00000020) | The file system supports per-user quotas. |
| **FILE_SUPPORTS_SPARSE_FILES** (0x00000040) | The file system supports sparse files. |
| **FILE_SUPPORTS_REPARSE_POINTS** (0x00000080) | The file system supports [reparse points](https://docs.microsoft.com/openspecs/windows_protocols/ms-smb/c7d64f17-1ab6-4151-b9e8-f15813235c83#gt_4fed0b53-5fc8-4818-886f-93d87f3035e1). |
| **FILE_SUPPORTS_REMOTE_STORAGE** (0x00000100) | The file system supports remote storage. |
| **FILE_RETURNS_CLEANUP_RESULT_INFO** (0x00000200) | On a successful cleanup operation, the file system returns information that describes additional actions taken during cleanup, such as deleting the file. File system filters can examine this information in their post-cleanup callback. |
| **FILE_SUPPORTS_POSIX_UNLINK_RENAME** (0x00000400) | The file system supports POSIX-style delete and rename operations. |
| **FILE_VOLUME_IS_COMPRESSED** (0x00008000) | The specified volume is a compressed volume. This flag is incompatible with the **FILE_FILE_COMPRESSION** flag. This does not affect how data is transferred over the network. |
| **FILE_SUPPORTS_OBJECT_IDS** (0x00010000) | The file system supports object identifiers. |
| **FILE_SUPPORTS_ENCRYPTION** (0x00020000) | The file system supports encryption. |
| **FILE_NAMED_STREAMS** (0x00040000) | The file system supports named [data streams](https://docs.microsoft.com/openspecs/windows_protocols/ms-smb/c7d64f17-1ab6-4151-b9e8-f15813235c83#gt_f3529cd8-50da-4f36-aa0b-66af455edbb6) for a file. |
| **FILE_READ_ONLY_VOLUME** (0x00080000) | The specified volume is read-only. |
| **FILE_SEQUENTIAL_WRITE_ONCE** (0x00100000) | The specified volume can be written to one time only. The write must be performed in sequential order. |
| **FILE_SUPPORTS_TRANSACTIONS** (0x00200000) | The file system supports [transaction processing](https://docs.microsoft.com/windows/desktop/FileIO/transactional-ntfs-portal). |
| **FILE_SUPPORTS_HARD_LINKS** (0x00400000) | The file system supports direct links to other devices and partitions. |
| **FILE_SUPPORTS_EXTENDED_ATTRIBUTES** (0x00800000) | The file system supports extended attributes (EAs). |
| **FILE_SUPPORTS_OPEN_BY_FILE_ID** (0x01000000) | The file system supports open by file ID. |
| **FILE_SUPPORTS_USN_JOURNAL** (0x02000000) | The file system supports update sequence number (USN) journals. |
| **FILE_SUPPORTS_INTEGRITY_STREAMS** (0x04000000) | The file system supports [integrity streams](https://docs.microsoft.com/windows-server/storage/refs/integrity-streams). |
| **FILE_SUPPORTS_BLOCK_REFCOUNTING** (0x08000000) | The file system supports [block cloning](https://docs.microsoft.com/windows/desktop/FileIO/block-cloning), that is, sharing logical clusters between files on the same volume. The file system reallocates on writes to shared clusters. |
| **FILE_SUPPORTS_SPARSE_VDL** (0x10000000) | The file system tracks whether each cluster of a file contains valid data (either from explicit file writes or automatic zeros) or invalid data (has not yet been written to or zeroed). File systems that use sparse valid data length (VDL) do not store a valid data length and do not require that valid data be contiguous within a file. |
| **FILE_DAX_VOLUME** (0x20000000)| The specified volume is a direct access (DAX) volume. |
| **FILE_SUPPORTS_GHOSTING** (0x40000000) | The file system supports ghosting. |

### -field MaximumComponentNameLength

Maximum file name component length, in bytes, supported by the specified file system. A file name component is that portion of a file name between path separator characters (such as backslashes).

### -field FileSystemNameLength

Length, in bytes, of the file system name. The value of this field must be greater than zero.

### -field FileSystemName

Variable-length Unicode field containing the name of the file system. This field is not null-terminated and must be handled as a sequence of **FileSystemNameLength** bytes.

## -remarks

This information can be queried in either of the following ways:

* Call [FltQueryVolumeInformation](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation) or [ZwQueryVolumeInformationFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwqueryvolumeinformationfile), passing **FileFsAttributeInformation** as the value of *FileInformationClass* and passing a caller-allocated, **FILE_FS_ATTRIBUTE_INFORMATION**-structured buffer as the value of *FileInformation*.

  * Note: On CSVFS, **FileFsAttributeInformation** returns **FILE_FS_ATTRIBUTE_INFORMATION** for the CSVFS file system. If you want to query **FileFsAttributeInformation** for the file system CSVFS is layered on then you should use [FSCTL_CSV_QUERY_DOWN_LEVEL_FILE_SYSTEM_CHARACTERISTICS](https://docs.microsoft.com/windows/win32/api/winioctl/ni-winioctl-fsctl_csv_query_down_level_file_system_characteristics).

* Create an IRP with major function code [IRP_MJ_QUERY_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information).

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume.

The size of the buffer passed in the *FileInformation* parameter to **FltQueryVolumeInformation** or **ZwQueryVolumeInformationFile** must be at least ```sizeof(FILE_FS_ATTRIBUTE_INFORMATION)```. Because a maximum file system name length cannot be assumed (practically, the limit is 2^31 character points), a second call to one of these routines will be required once *FileSystemNameLength* is known.

This structure must be aligned on a **LONG** (4-byte) boundary.

## -see-also

[ACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)

[FltQueryVolumeInformation](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation)

[IRP_MJ_QUERY_VOLUME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[ZwQueryVolumeInformationFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwqueryvolumeinformationfile)
