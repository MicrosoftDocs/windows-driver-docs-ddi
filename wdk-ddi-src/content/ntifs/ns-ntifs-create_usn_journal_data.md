---
UID: NS:ntifs.CREATE_USN_JOURNAL_DATA
tech.root: ifsk
title: CREATE_USN_JOURNAL_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the CREATE_USN_JOURNAL_DATA structure.
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
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: CREATE_USN_JOURNAL_DATA, *PCREATE_USN_JOURNAL_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - CREATE_USN_JOURNAL_DATA
 - PCREATE_USN_JOURNAL_DATA
f1_keywords:
 - CREATE_USN_JOURNAL_DATA
 - ntifs/CREATE_USN_JOURNAL_DATA
 - PCREATE_USN_JOURNAL_DATA
 - ntifs/PCREATE_USN_JOURNAL_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - CREATE_USN_JOURNAL_DATA
---

## -description

The **CREATE_USN_JOURNAL_DATA** structure contains information for the creation of an update sequence number (USN) change journal.

## -struct-fields

### -field MaximumSize

The target maximum size that the NTFS file system allocates for the change journal, in bytes.

### -field AllocationDelta

The size of memory allocation that is added to the end and removed from the beginning of the change journal, in bytes.

The change journal can grow to more than the sum of the values of **MaximumSize** and **AllocationDelta** before being trimmed.

## -remarks

For more information, see [Creating, Modifying, and Deleting a Change Journal](/windows/win32/fileio/creating-modifying-and-deleting-a-change-journal).

## -see-also

[**FSCTL_CREATE_USN_JOURNAL**](ni-ntifs-fsctl_create_usn_journal.md)
