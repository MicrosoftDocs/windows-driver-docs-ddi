---
UID: NS:ntifs.USN_JOURNAL_DATA_V2
tech.root: ifsk
title: USN_JOURNAL_DATA_V2
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the USN_JOURNAL_DATA_V2 structure.
prerelease: false
req.construct-type: strsucture
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: USN_JOURNAL_DATA_V2, *PUSN_JOURNAL_DATA_V2
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
 - USN_JOURNAL_DATA_V2
 - PUSN_JOURNAL_DATA_V2
f1_keywords:
 - USN_JOURNAL_DATA_V2
 - ntifs/USN_JOURNAL_DATA_V2
 - PUSN_JOURNAL_DATA_V2
 - ntifs/PUSN_JOURNAL_DATA_V2
dev_langs:
 - c++
helpviewer_keywords:
 - USN_JOURNAL_DATA_V2
---

## -description

The **USN_JOURNAL_DATA_V2** structure represents an update sequence number (USN) change journal, its records, and its capacity. This structure is the output buffer for the [**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md) control code.

## -struct-fields

### -field UsnJournalID

The current journal identifier. A journal is assigned a new identifier on creation and can be stamped with a new identifier in the course of its existence. The NTFS file system uses this identifier for an integrity check.

### -field FirstUsn

The number of first record that can be read from the journal.

### -field NextUsn

The number of next record to be written to the journal.

### -field LowestValidUsn

The first record that was written into the journal for this journal instance. Enumerating the files or directories on a volume can return a USN lower than this value (in other words, a **FirstUsn** member value less than the **LowestValidUsn** member value). If it does, the journal has been stamped with a new identifier since the last USN was written. In this case, **LowestValidUsn** may indicate a discontinuity in the journal, in which changes to some or all files or directories on the volume may have occurred that are not recorded in the change journal.

### -field MaxUsn

The largest USN that the change journal supports. An administrator must delete the change journal as the value of **NextUsn** approaches this value.

### -field MaximumSize

The target maximum size for the change journal, in bytes. The change journal can grow larger than this value, but it is then truncated at the next NTFS file system checkpoint to less than this value.

### -field AllocationDelta

The number of bytes of disk memory added to the end and removed from the beginning of the change journal each time memory is allocated or deallocated. In other words, allocation and deallocation take place in units of this size. An integer multiple of a cluster size is a reasonable value for this member.

### -field MinSupportedMajorVersion

The minimum major version of the USN Journal that is supported by the system. This field helps ensure that the journal data being processed isn't from an unsupported older version.

### -field MaxSupportedMajorVersion

The maximum major version of the USN Journal that is supported by the system. This field helps ensure that the journal data being processed isn't from a newer version that the system doesn't support.

### -field Flags

Flags that indicate whether range tracking is turned on. The following are the possible values for the Flags member.

| Value | Meaning |
|-------|---------|
| 0x00000000 | Range tracking is not turned on for the volume. |
| FLAG_USN_TRACK_MODIFIED_RANGES_ENABLE (0x01) | Range tracking is turned on for the volume. |

### -field RangeTrackChunkSize

The granularity of tracked ranges. Valid only when you also set the **Flags** member to FLAG_USN_TRACK_MODIFIED_RANGES_ENABLE.

### -field RangeTrackFileSizeThreshold

File size threshold to start tracking range for files with equal or larger size. Valid only when you also set the **Flags** member to FLAG_USN_TRACK_MODIFIED_RANGES_ENABLE.

## -see-also

[**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md)

[**USN_JOURNAL_DATA_V0**](ns-ntifs-usn_journal_data_v0.md)

[**USN_JOURNAL_DATA_V1**](ns-ntifs-usn_journal_data_v1.md)
