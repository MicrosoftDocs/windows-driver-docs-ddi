---
UID: NS:ntifs._FILE_DIRECTORY_INFORMATION
title: _FILE_DIRECTORY_INFORMATION (ntifs.h)
description: The FILE_DIRECTORY_INFORMATION structure is used to query detailed information for the files in a directory.
old-location: ifsk\file_directory_information.htm
tech.root: ifsk
ms.assetid: 012c3178-f3a0-449b-b4a2-91fff4af1a17
ms.date: 04/16/2018
ms.keywords: "*PFILE_DIRECTORY_INFORMATION, FILE_DIRECTORY_INFORMATION, FILE_DIRECTORY_INFORMATION structure [Installable File System Drivers], PFILE_DIRECTORY_INFORMATION, PFILE_DIRECTORY_INFORMATION structure pointer [Installable File System Drivers], _FILE_DIRECTORY_INFORMATION, fileinformationstructures_4ff53e27-9b59-46f0-8ca8-b4e1fb3e3905.xml, ifsk.file_directory_information, ntifs/FILE_DIRECTORY_INFORMATION, ntifs/PFILE_DIRECTORY_INFORMATION"
ms.topic: struct
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
- FILE_DIRECTORY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_DIRECTORY_INFORMATION, *PFILE_DIRECTORY_INFORMATION
---

# _FILE_DIRECTORY_INFORMATION structure

## -description

The FILE_DIRECTORY_INFORMATION structure is used to query detailed information for the files in a directory.

## -struct-fields

### -field NextEntryOffset

Byte offset of the next FILE_DIRECTORY_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one.

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

* FILE_ATTRIBUTE_ARCHIVE
* FILE_ATTRIBUTE_COMPRESSED
* FILE_ATTRIBUTE_DIRECTORY
* FILE_ATTRIBUTE_HIDDEN
* FILE_ATTRIBUTE_NORMAL
* FILE_ATTRIBUTE_READONLY
* FILE_ATTRIBUTE_SYSTEM
* FILE_ATTRIBUTE_TEMPORARY

### -field FileNameLength

Specifies the length of the file name string.

### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.

## -remarks

This information can be queried in either of the following ways:

* Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>, passing FileDirectoryInformation as the value of *FileInformationClass* and passing a caller-allocated, FILE_DIRECTORY_INFORMATION-structured buffer as the value of *FileInformation*.
* Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY.

No specific access rights are required to query this information.

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601.

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the **NextEntryOffset** value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>
