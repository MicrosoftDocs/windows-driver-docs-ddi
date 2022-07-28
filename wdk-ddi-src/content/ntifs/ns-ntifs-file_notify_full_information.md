---
UID: NS:ntifs._FILE_NOTIFY_FULL_INFORMATION
tech.root: ifsk
title: FILE_NOTIFY_FULL_INFORMATION
ms.date: 06/21/2022
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
req.target-min-winverclnt: Windows 11, version 22H2
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

**FILE_NOTIFY_FULL_INFORMATION** describes detailed changes found by the [**ReadDirectoryChangesExW**](/windows/win32/api/winbase/nf-winbase-readdirectorychangesexw) and [**ZwNotifyChangeDirectoryFileEx**](/previous-versions/mt812581(v%3dvs.85)) functions.

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

### -field CreationTime

The date and time when the directory or file was created and added to the file system.

### -field LastModificationTime

The date and time that the content of the directory or file was last modified in the file system.

### -field LastChangeTime

The date and time that the metadata or content of the directory or file was last changed in the file system.

### -field LastAccessTime

The date and time the directory or file was last accessed in the file system.

### -field AllocatedLength

The allocated size of the file, in bytes.

### -field FileSize

The new size of the directory or file in bytes, or the old size if the size is unchanged.

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

The identifier tag of a reparse point for the directory or file.

### -field DUMMYUNIONNAME.EaSize

Combined length of the extended attributes (EA) for the file, in bytes.

### -field FileId

The identifier of the directory or file. This number is generated and assigned to the file by the file system.

### -field ParentFileId

The identifier of the parent directory of the file.

### -field FileNameLength

The size of the file name portion of the record, in bytes. This value does not include a terminating null character.

### -field FileNameFlags

Flags specifying what type of file name is being returned, if known. If neither of the following flags is set, the type of file name is not known. If both of the following flags are set, the file name acts as both the long name and the short name (both the NTFS name and the DOS name) of a long/short name pair.

| Flag | Value |
| ---- | ----- |
| FILE_NAME_NTFS (0x01) | The file name is the long name (NTFS name) of a long/short name pair. |
| FILE_NAME_DOS (0x02)  | The file name is the short name (DOS name) of a long/short name pair. |

### -field Reserved

Reserved for system use.

### -field FileName

A variable-length field that contains the file name relative to the directory handle. The file name is in the Unicode character format and is not null-terminated.

## -remarks

A **FILE_NOTIFY_FULL_INFORMATION** structure is returned in response to an [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) request with an **IRP_MN_NOTIFY_CHANGE_DIRECTORY** minor function code when DIRECTORY_NOTIFY_INFORMATION_CLASS=DirectoryNotifyFullInformation.

## -see-also

[**DIRECTORY_NOTIFY_INFORMATION_CLASS**](../wdm/ne-wdm-_directory_notify_information_class.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**ZwNotifyChangeDirectoryFileEx**](/previous-versions/mt812581(v=vs.85))
