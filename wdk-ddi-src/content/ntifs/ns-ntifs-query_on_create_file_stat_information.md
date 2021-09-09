---
UID: NS:ntifs._QUERY_ON_CREATE_FILE_STAT_INFORMATION
tech.root: ifsk
title: QUERY_ON_CREATE_FILE_STAT_INFORMATION
ms.date: 03/11/2021
targetos: Windows
description: The QUERY_ON_CREATE_FILE_STAT_INFORMATION structure is used to write file information when FltRequestFileInfoOnCreateCompletion is called with the QoCFileStatInformation flag set in the InfoClassFlags parameter.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_ON_CREATE_FILE_STAT_INFORMATION, *PQUERY_ON_CREATE_FILE_STAT_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_ON_CREATE_FILE_STAT_INFORMATION
 - PQUERY_ON_CREATE_FILE_STAT_INFORMATION
 - QUERY_ON_CREATE_FILE_STAT_INFORMATION
f1_keywords:
 - _QUERY_ON_CREATE_FILE_STAT_INFORMATION
 - ntifs/_QUERY_ON_CREATE_FILE_STAT_INFORMATION
 - PQUERY_ON_CREATE_FILE_STAT_INFORMATION
 - ntifs/PQUERY_ON_CREATE_FILE_STAT_INFORMATION
 - QUERY_ON_CREATE_FILE_STAT_INFORMATION
 - ntifs/QUERY_ON_CREATE_FILE_STAT_INFORMATION
dev_langs:
 - c++
---

## -description

The **QUERY_ON_CREATE_FILE_STAT_INFORMATION** structure is used to write file information when [**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md) is called with the **QoCFileStatInformation** flag set in the **InfoClassFlags** parameter.

## -struct-fields

### -field FileId

The ID of the file.

### -field CreationTime

The creation time of the file.

### -field LastAccessTime

The time that the file was last accessed.

### -field LastWriteTime

The last time that the file was written to.

### -field ChangeTime

The last time a file was changed.

### -field AllocationSize

The file allocation size, in bytes. Usually this value is a multiple of the sector or cluster size of the underlying physical device.

### -field EndOfFile

The absolute, new end-of-file position as a byte offset from the start of the file. **EndOfFile** specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, **EndOfFile** is the offset to the byte immediately following the last valid byte in the file.

### -field FileAttributes

The file's attributes, which can be any valid combination of the following values.

| Attribute | Meaning |
| --------- | ------- |
| FILE_ATTRIBUTE_READONLY (0x00000001) | The file is read-only. |
| FILE_ATTRIBUTE_HIDDEN (0x00000002) | The file or directory is hidden. |
| FILE_ATTRIBUTE_SYSTEM (0x00000004) | The file or directory is partially or exclusively used by the operating system. |
| FILE_ATTRIBUTE_DIRECTORY (0x00000010) | Identifies a directory. |
| FILE_ATTRIBUTE_ARCHIVE (0x00000020) | A file or directory marked for archive. |
| FILE_ATTRIBUTE_NORMAL (0x00000080) | A file that does not have other attributes set. This attribute is valid only when used alone. |

### -field ReparseTag

Reparse point tag. See [About reparse points](/windows-hardware/drivers/ifs/reparse-points) for more information.

### -field NumberOfLinks

The number of links to the file.

## -remarks

The file system allocates this structure and fills in the requested information, if supported, while it processes a file create. Filter Manager will free the allocated structure.

## -see-also

[**FILE_STAT_INFORMATION**](ns-ntifs-_file_stat_information.md)

[**FltRequestFileInfoOnCreateCompletion**](../fltkernel/nf-fltkernel-fltrequestfileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](../fltkernel/nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)
