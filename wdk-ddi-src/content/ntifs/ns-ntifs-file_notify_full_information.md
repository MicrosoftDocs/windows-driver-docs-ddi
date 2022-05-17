---
UID: NS:ntifs._FILE_NOTIFY_FULL_INFORMATION
tech.root: ifsk
title: FILE_NOTIFY_FULL_INFORMATION
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the FILE_NOTIFY_FULL_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: FILE_NOTIFY_FULL_INFORMATION, *PFILE_NOTIFY_FULL_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_NOTIFY_FULL_INFORMATION
 - PFILE_NOTIFY_FULL_INFORMATION
 - FILE_NOTIFY_FULL_INFORMATION
f1_keywords:
 - _FILE_NOTIFY_FULL_INFORMATION
 - ntifs/_FILE_NOTIFY_FULL_INFORMATION
 - PFILE_NOTIFY_FULL_INFORMATION
 - ntifs/PFILE_NOTIFY_FULL_INFORMATION
 - FILE_NOTIFY_FULL_INFORMATION
 - ntifs/FILE_NOTIFY_FULL_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _FILE_NOTIFY_FULL_INFORMATION
---

## -description

**FILE_NOTIFY_FULL_INFORMATION** describes detailed changes to a directory.

## -struct-fields

### -field NextEntryOffset

The number of bytes that must be skipped to get to the next record. A value of zero indicates that this is the last record.

### -field Action

The type of change that has occurred. This member can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| FILE_ACTION_ADDED (0x00000001) | A file was added to the directory. |
| FILE_ACTION_REMOVED (0x00000002) | A file was removed from the directory. |
| FILE_ACTION_MODIFIED (0x00000003) | The directory was modified. This can be a change in the time stamp or attributes. |
| FILE_ACTION_RENAMED_OLD_NAME (0x00000004) | The directory was renamed and this is the old name. |
| FILE_ACTION_RENAMED_NEW_NAME (0x00000005) | The directory was renamed and this is the new name. |
| FILE_ACTION_ADDED_STREAM (0x00000006) | A named stream was added to the directory. |
| FILE_ACTION_REMOVED_STREAM (0x00000007) | A named stream was removed from the directory. |
| FILE_ACTION_MODIFIED_STREAM (0x00000008) | A named stream was modified. The modification can be a change to the data or attributes of the named stream. |
| FILE_ACTION_REMOVED_BY_DELETE (0x00000009) | An object ID was removed because the directory the object ID referred to was deleted. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |
| FILE_ACTION_ID_NOT_TUNNELLED (0x0000000A) | An attempt to tunnel object ID information to a file being created or renamed failed because the object ID is in use by another file on the same volume. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |
| FILE_ACTION_TUNNELLED_ID_COLLISION (0x0000000B) | An attempt to tunnel object ID information to a directory being renamed failed because the directory already has an object ID. This notification is only sent when the directory being monitored is the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION". |

### -field CreationTime

The time when the file was created.

### -field LastModificationTime

The time when the contents of the file were last modified.

### -field LastChangeTime

The time when the status of the file was last modified. Status can include content changes as well as file permissions and ownership.

### -field LastAccessTime

The time when the file was last accessed.

### -field AllocatedLength

File allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device.

### -field FileSize

Size of the actual file contents, in bytes.

### -field FileAttributes

File attributes, which can be any valid combination of the following:

* FILE_ATTRIBUTE_READONLY
* FILE_ATTRIBUTE_HIDDEN
* FILE_ATTRIBUTE_SYSTEM
* FILE_ATTRIBUTE_DIRECTORY
* FILE_ATTRIBUTE_ARCHIVE
* FILE_ATTRIBUTE_NORMAL
* FILE_ATTRIBUTE_TEMPORARY
* FILE_ATTRIBUTE_COMPRESSED

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.ReparsePointTag

Tag value for the reparse point.

### -field DUMMYUNIONNAME.EaSize

Combined length of the extended attributes (EA) for the file, in bytes.

### -field FileId

The 128-byte file reference number for the file. This number is generated and assigned to the file by the file system.

### -field ParentFileId

The 128-byte file reference number for the parent directory of the file.

### -field FileNameLength

The size of the file name, in bytes. This value does not include the terminating null character.

### -field FileNameFlags

### -field Reserved

Reserved for system use.

### -field FileName

A variable-length field that contains the file name relative to the directory handle. The file name is in the Unicode character format and is not null-terminated.

If there is both a short and long name for the file, only one of these names will be returned, but it is unspecified which one.

## -remarks

A **FILE_NOTIFY_FULL_INFORMATION** structure is returned in response to an [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) request with an **IRP_MN_NOTIFY_CHANGE_DIRECTORY** minor function code when DIRECTORY_NOTIFY_INFORMATION_CLASS=DirectoryNotifyFullInformation.

## -see-also

[**DIRECTORY_NOTIFY_INFORMATION_CLASS**](../wdm/ne-wdm-_directory_notify_information_class.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**ZwNotifyChangeDirectoryFileEx **](/previous-versions/mt812581(v=vs.85))
