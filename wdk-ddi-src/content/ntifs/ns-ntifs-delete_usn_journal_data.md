---
UID: NS:ntifs.DELETE_USN_JOURNAL_DATA
tech.root: ifsk
title: DELETE_USN_JOURNAL_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the DELETE_USN_JOURNAL_DATA structure.
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
req.typenames: DELETE_USN_JOURNAL_DATA, *PDELETE_USN_JOURNAL_DATA
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
 - DELETE_USN_JOURNAL_DATA
 - PDELETE_USN_JOURNAL_DATA
f1_keywords:
 - DELETE_USN_JOURNAL_DATA
 - ntifs/DELETE_USN_JOURNAL_DATA
 - PDELETE_USN_JOURNAL_DATA
 - ntifs/PDELETE_USN_JOURNAL_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - DELETE_USN_JOURNAL_DATA
---

## -description

The **DELETE_USN_JOURNAL_DATA** structure contains information for the deletion of an update sequence number (USN) change journal.

## -struct-fields

### -field UsnJournalID

The identifier of the change journal to be deleted.

If the journal is active and deletion is requested by setting the **USN_DELETE_FLAG_DELETE** flag in the **DeleteFlags** member, then this identifier must specify the change journal for the current volume. Use [**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md)
 to retrieve the identifier of this change journal. If in this case the identifier is not for the current volume's change journal, **FSCTL_DELETE_USN_JOURNAL** fails.

If notification instead of deletion is requested by setting only the **USN_DELETE_FLAG_NOTIFY** flag in **DeleteFlags**, **UsnJournalID** is ignored.

### -field DeleteFlags

Indicates whether deletion or notification regarding deletion is performed, or both. The **DeleteFlags** member must contain one or both of the following values.

|Value | Meaning |
| ---- | ------- |
| USN_DELETE_FLAG_DELETE (0x00000001) | If this flag is set and USN_DELETE_FLAG_NOTIFY is not set, the [**FSCTL_DELETE_USN_JOURNAL**](ni-ntifs-fsctl_delete_usn_journal.md) operation starts the journal deletion process and returns immediately. The journal deletion process continues, if necessary, across system restarts. If this flag is set and the USN_DELETE_FLAG_NOTIFY flag is also set, both deletion and notification occur. If this flag is set and the journal is active, you must provide the identifier for the change journal for the current volume in **UsnJournalID** or the operation fails. If the journal is not active, then **UsnJournalID** is ignored and the journal is deleted. |
| USN_DELETE_FLAG_NOTIFY (0x00000002) | If this flag is set, the call sets up notification about when deletion is complete. The journal deletion request is completed when the journal deletion process is complete. If this flag is set and the **USN_DELETE_FLAG_DELETE** flag is not set, then the call sets up notification of a deletion that may already be in progress. For example, when your application starts, it might use this flag to determine if a deletion is in progress. If this flag is set and the USN_DELETE_FLAG_DELETE flag is also set, both deletion and notification occur. The notification is performed using an I/O completion port or another mechanism for asynchronous event notification. |

## -remarks

For more information, see [Creating, Modifying, and Deleting a Change Journal](/windows/win32/fileio/creating-modifying-and-deleting-a-change-journal).

## -see-also

[**FSCTL_DELETE_USN_JOURNAL**](ni-ntifs-fsctl_delete_usn_journal.md)

[**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md)
