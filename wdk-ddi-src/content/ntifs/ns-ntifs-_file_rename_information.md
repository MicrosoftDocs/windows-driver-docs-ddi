---
UID: NS:ntifs._FILE_RENAME_INFORMATION
title: FILE_RENAME_INFORMATION (ntifs.h)
description: The FILE_RENAME_INFORMATION structure is used to rename a file.
old-location: ifsk\file_rename_information.htm
tech.root: ifsk
ms.date: 11/22/2021
keywords: ["FILE_RENAME_INFORMATION structure"]
ms.keywords: "*PFILE_RENAME_INFORMATION, FILE_RENAME_INFORMATION, FILE_RENAME_INFORMATION structure [Installable File System Drivers], PFILE_RENAME_INFORMATION, PFILE_RENAME_INFORMATION structure pointer [Installable File System Drivers], _FILE_RENAME_INFORMATION, fileinformationstructures_d9a99263-5aec-400a-ab30-73949a81a4f6.xml, ifsk.file_rename_information, ntifs/FILE_RENAME_INFORMATION, ntifs/PFILE_RENAME_INFORMATION"
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
targetos: Windows
req.typenames: FILE_RENAME_INFORMATION, *PFILE_RENAME_INFORMATION
ms.custom: 19H1
f1_keywords:
 - _FILE_RENAME_INFORMATION
 - ntifs/_FILE_RENAME_INFORMATION
 - PFILE_RENAME_INFORMATION
 - ntifs/PFILE_RENAME_INFORMATION
 - FILE_RENAME_INFORMATION
 - ntifs/FILE_RENAME_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_RENAME_INFORMATION
 - PFILE_RENAME_INFORMATION
 - FILE_RENAME_INFORMATION
dev_langs:
 - c++
---

# FILE_RENAME_INFORMATION structure

## -description

The **FILE_RENAME_INFORMATION** structure is used to rename a file.

## -struct-fields

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.ReplaceIfExists

Set to TRUE to specify that if a file with the given name already exists, it should be replaced with the given file. Set to FALSE if the rename operation should fail if a file with the given name already exists.

### -field DUMMYUNIONNAME.Flags

Flags for the rename operation.  This field is only applicable when used with the **FileRenameInformationEx** information class.

Here are the possible values:

| Value | Meaning |
| ----- | ------- |
| **FILE_RENAME_REPLACE_IF_EXISTS** (0x00000001) | If a file with the given name already exists, it should be replaced with the given file.  Equivalent to the ReplaceIfExists field used with the FileRenameInformation information class. |
| **FILE_RENAME_POSIX_SEMANTICS** (0x00000002) | If FILE_RENAME_REPLACE_IF_EXISTS is also specified, allow replacing a file even if there are existing handles to it.  Existing handles to the replaced file continue to be valid for operations such as read and write.  Any subsequent opens of the target name will open the renamed file, not the replaced file. |
| **FILE_RENAME_SUPPRESS_PIN_STATE_INHERITANCE** (0x00000004) | When renaming a file to a new directory, suppress any inheritance rules related to the FILE_ATTRIBUTE_PINNED and FILE_ATTRIBUTE_UNPINNED attributes of the file. |
| **FILE_RENAME_SUPPRESS_STORAGE_RESERVE_INHERITANCE** (0x00000008) | When renaming a file to a new directory, suppress any inheritance rules related to the storage reserve ID property of the file. |
| **FILE_RENAME_NO_INCREASE_AVAILABLE_SPACE** (0x00000010) | If FILE_RENAME_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when renaming a file to a new directory, automatically resize affected storage reserve areas as needed to prevent the user visible free space on the volume from increasing.  Requires manage volume access. |
| **FILE_RENAME_NO_DECREASE_AVAILABLE_SPACE** (0x00000020) | If FILE_RENAME_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when renaming a file to a new directory, automatically resize affected storage reserve areas as needed to prevent the user visible free space on the volume from decreasing.  Requires manage volume access. |
| **FILE_RENAME_PRESERVE_AVAILABLE_SPACE** (0x00000030) | Equivalent to specifying both FILE_RENAME_NO_INCREASE_AVAILABLE_SPACE and FILE_RENAME_NO_DECREASE_AVAILABLE_SPACE. |
| **FILE_RENAME_IGNORE_READONLY_ATTRIBUTE** (0x00000040) | If FILE_RENAME_REPLACE_IF_EXISTS is also specified, allow replacing a file even if it is read-only.  Requires WRITE_ATTRIBUTES access to the replaced file. |
| **FILE_RENAME_FORCE_RESIZE_TARGET_SR** (0x00000080) | If FILE_RENAME_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when renaming a file to a new directory that is part of a different storage reserve area, always grow the target directory's storage reserve area by the full size of the file being renamed.  Requires manage volume access. |
| **FILE_RENAME_FORCE_RESIZE_SOURCE_SR** (0x00000100) | If FILE_RENAME_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when renaming a file to a new directory that is part of a different storage reserve area, always shrink the source directory's storage reserve area by the full size of the file being renamed.  Requires manage volume access. |
| **FILE_RENAME_FORCE_RESIZE_SR** (0x00000180) | Equivalent to specifying both FILE_RENAME_FORCE_RESIZE_TARGET_SR and FILE_RENAME_FORCE_RESIZE_SOURCE_SR. |

### -field ReplaceIfExists

Set to TRUE to specify that if a file with the given name already exists, it should be replaced with the given file. Set to FALSE if the rename operation should fail if a file with the given name already exists.

### -field RootDirectory

A handle that **IopOpenLinkOrRenameTarget** uses to open the target directory.

If the file is not being moved to a different directory, or if the **FileName** member contains the full pathname, this member is NULL. Otherwise, it is a handle for the root directory under which the file will reside after it is renamed.

To perform two open operations that won't cause a sharing conflict, you can open **RootDirectory** by requesting traverse | read-attribute. **IopOpenLinkOrRenameTarget** can then perform a relative open by requesting FILE_WRITE_DATA | SYNCHRONIZE. These two opens would not cause sharing conflict.

### -field FileNameLength

Length, in bytes, of the new name for the file.

### -field FileName

The first character of a wide-character string containing the new name for the file. This is followed in memory by the remainder of the string. If the **RootDirectory** member is NULL, and the file is being moved to a different directory, this member specifies the full pathname to be assigned to the file. Otherwise, it specifies only the file name or a relative pathname.

## -syntax

```cpp
typedef struct _FILE_RENAME_INFORMATION {
#if (_WIN32_WINNT >= _WIN32_WINNT_WIN10_RS1)
    union {
        BOOLEAN ReplaceIfExists;  // FileRenameInformation
        ULONG Flags;              // FileRenameInformationEx
    } DUMMYUNIONNAME;
#else
    BOOLEAN ReplaceIfExists;
#endif
    HANDLE RootDirectory;
    ULONG FileNameLength;
    WCHAR FileName[1];
} FILE_RENAME_INFORMATION, *PFILE_RENAME_INFORMATION;

```

## -remarks

The **FILE_RENAME_INFORMATION** structure is used to rename a file. This operation can be performed in either of the following ways:

* Call [**FltSetInformationFile**](../fltkernel/nf-fltkernel-fltsetinformationfile.md) or [**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md), passing **FileRenameInformation** as the value of **FileInformationClass** and passing a caller-allocated buffer formatted as a **FILE_RENAME_INFORMATION** structure for the value of **FileInformation**. The **FileHandle** parameter specifies the file to be renamed.

* Create an IRP with major function code [**IRP_MJ_SET_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-information).

File system minifilters must use [**FltSetInformationFile**](../fltkernel/nf-fltkernel-fltsetinformationfile.md), not [**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md), to rename a file.

Renaming a file requires DELETE access to the file so that the directory entry can be removed from the current parent directory, as well as the appropriate access to create the new entry in the new parent directory file.

The file name string in the **FileName** member must be specified in one of the following forms.

* A simple file name. (The **RootDirectory** member is NULL.) In this case, the file is simply renamed within the same directory. That is, the rename operation changes the name of the file but not its location.

* A fully qualified file name. (The **RootDirectory** member is NULL.) In this case, the rename operation changes the name and location of the file.

* A relative file name. In this case, the **RootDirectory** member contains a handle to the target directory for the rename operation. The file name itself must be a simple file name.

General rules for rename operations:

* A file or directory can only be renamed within a volume. In other words, a rename operation cannot cause a file or directory to be moved to a different volume.

* A volume's root directory cannot be renamed.

* If **ReplaceIfExists** is set to FALSE, and the target exists, the rename operation will fail.

* Even if **ReplaceIfExists** is set to TRUE, the rename operation will still fail if a file with the same name already exists and is a directory, a read-only file, or a currently executing file.

* A volume's files and directories cannot be renamed if the volume is a read-only volume, such as a CDFS volume or a read-only NTFS volume.

Special rules for renaming open files:

* A file cannot be renamed if it has any open handles, unless it is only open because of a batch opportunistic lock (oplock) and the batch oplock can be broken immediately.

* A file cannot be renamed if a file with the same name exists and has open handles (except in the batch-oplock case described earlier).

* A directory cannot be renamed if it or any of its subdirectories contains a file that has open handles (except in the batch-oplock case described earlier).

Special rules for renaming NTFS data streams:

* The default directory stream cannot be renamed.

* The new name for the stream must begin with a colon (:).

* A data stream can only be renamed *within* the same file. In other words, a rename operation cannot cause a data stream to be moved to a different file.

* A data stream on a directory cannot be renamed to the default data stream.

* If **ReplaceIfExists** is set to TRUE, the rename operation will succeed only if a stream with the same name does not exist or is a zero-length data stream.

* "Renaming" the default data stream is allowed, but this is not a true rename, because it leaves behind a zero-length default data stream.

The size of the **FileInformation** buffer passed to [**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md) or [**FltSetInformationFile**](../fltkernel/nf-fltkernel-fltsetinformationfile.md) must be >= **sizeof**(FILE_RENAME_INFORMATION) plus the size in bytes of the **FileName** string.

## -see-also

[**FltSetInformationFile**](../fltkernel/nf-fltkernel-fltsetinformationfile.md)

[**IRP_MJ_SET_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-information)

[**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md)
