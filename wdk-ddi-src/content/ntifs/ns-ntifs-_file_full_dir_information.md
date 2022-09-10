---
UID: NS:ntifs._FILE_FULL_DIR_INFORMATION
title: FILE_FULL_DIR_INFORMATION (ntifs.h)
description: The FILE_FULL_DIR_INFORMATION structure is used to query detailed information for the files in a directory.
old-location: ifsk\file_full_dir_information.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["FILE_FULL_DIR_INFORMATION structure"]
ms.keywords: "*PFILE_FULL_DIR_INFORMATION, FILE_FULL_DIR_INFORMATION, FILE_FULL_DIR_INFORMATION structure [Installable File System Drivers], PFILE_FULL_DIR_INFORMATION, PFILE_FULL_DIR_INFORMATION structure pointer [Installable File System Drivers], _FILE_FULL_DIR_INFORMATION, fileinformationstructures_2dfa5780-08bf-4cb8-96f6-c247baaa813a.xml, ifsk.file_full_dir_information, ntifs/FILE_FULL_DIR_INFORMATION, ntifs/PFILE_FULL_DIR_INFORMATION"
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
req.typenames: FILE_FULL_DIR_INFORMATION, *PFILE_FULL_DIR_INFORMATION
f1_keywords:
 - _FILE_FULL_DIR_INFORMATION
 - ntifs/_FILE_FULL_DIR_INFORMATION
 - PFILE_FULL_DIR_INFORMATION
 - ntifs/PFILE_FULL_DIR_INFORMATION
 - FILE_FULL_DIR_INFORMATION
 - ntifs/FILE_FULL_DIR_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_FULL_DIR_INFORMATION
 - PFILE_FULL_DIR_INFORMATION
 - FILE_FULL_DIR_INFORMATION
---

# FILE_FULL_DIR_INFORMATION structure

## -description

The **FILE_FULL_DIR_INFORMATION** structure is used to query detailed information for the files in a directory.

## -struct-fields

### -field NextEntryOffset

Byte offset of the next **FILE_FULL_DIR_INFORMATION** entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

### -field FileIndex

Byte offset of the file within the parent directory. This member is undefined for file systems, such as NTFS, in which the position of a file within the parent directory is not fixed and can be changed at any time to maintain sort order.

### -field CreationTime

Time when the file was created.

### -field LastAccessTime

Last time the file was accessed.

### -field LastWriteTime

Last time information was written to the file.

### -field ChangeTime

Last time the file was changed.

### -field EndOfFile

Absolute new end-of-file position as a byte offset from the start of the file. **EndOfFile** specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, **EndOfFile** is the offset to the byte immediately following the last valid byte in the file.

### -field AllocationSize

File allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device.

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

### -field FileNameLength

Specifies the length of the file name string.

### -field EaSize

Combined length, in bytes, of the extended attributes (EA) for the file.

### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.

## -remarks

This information can be queried in either of the following ways:

* Call [**ZwQueryDirectoryFile**](nf-ntifs-zwqueryvirtualmemory.md), passing FileFullDirectoryInformation as the value of **FileInformationClass** and passing a caller-allocated, FILE_FULL_DIR_INFORMATION-structured buffer as the value of **FileInformation**.

* Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY.

No specific access rights are required to query this information.

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601.

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the **NextEntryOffset** value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

[**FsRtlNotifyFullChangeDirectory**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**ZwQueryDirectoryFile**](nf-ntifs-zwqueryvirtualmemory.md)
