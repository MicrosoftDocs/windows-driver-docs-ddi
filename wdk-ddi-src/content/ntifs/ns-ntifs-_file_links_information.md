---
UID: NS:ntifs._FILE_LINKS_INFORMATION
title: FILE_LINKS_INFORMATION (ntifs.h)
description: Learn more about the FILE_LINKS_INFORMATION structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FILE_LINKS_INFORMATION structure"]
ms.keywords: "*PFILE_LINKS_INFORMATION, FILE_LINKS_INFORMATION, FILE_LINKS_INFORMATION structure [Installable File System Drivers], PFILE_LINKS_INFORMATION, PFILE_LINKS_INFORMATION structure pointer [Installable File System Drivers], _FILE_LINKS_INFORMATION, ifsk.file_links_information, ntifs/FILE_LINKS_INFORMATION, ntifs/PFILE_LINKS_INFORMATION"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: FILE_LINKS_INFORMATION, *PFILE_LINKS_INFORMATION
f1_keywords:
 - _FILE_LINKS_INFORMATION
 - ntifs/_FILE_LINKS_INFORMATION
 - PFILE_LINKS_INFORMATION
 - ntifs/PFILE_LINKS_INFORMATION
 - FILE_LINKS_INFORMATION
 - ntifs/FILE_LINKS_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_LINKS_INFORMATION
 - PFILE_LINKS_INFORMATION
 - FILE_LINKS_INFORMATION
---

# FILE_LINKS_INFORMATION structure

## -description

The **FILE_LINKS_INFORMATION** structure is used to query or set researchNTFS hard links to an existing file.

## -struct-fields

### -field BytesNeeded

The number of bytes needed to hold all available names returned in **Entry**. This value must be greater than 0.

### -field EntriesReturned

The number of [**FILE_LINK_ENTRY_INFORMATION**](ns-ntifs-_file_link_entry_information.md) structures that have been returned using the **Entry** member.

### -field Entry

A buffer that contains the returned [**FILE_LINK_ENTRY_INFORMATION**](ns-ntifs-_file_link_entry_information.md) structures.

## -remarks

If **EntriesReturned** has a value of 0, there is not enough available memory to return an entry. The error STATUS_BUFFER_OVERFLOW (0x80000005) indicates that not all available entries were returned.

**Entry** is the first [**FILE_LINK_ENTRY_INFORMATION**](ns-ntifs-_file_link_entry_information.md) structure in a list of entries. If an entry’s **NextEntryOffset** field has a value of 0, no further entries were returned; otherwise, the next entry returned is located **NextEntryOffset** bytes from the previous entry.

## -see-also

[**FILE_LINK_ENTRY_INFORMATION**](ns-ntifs-_file_link_entry_information.md)
