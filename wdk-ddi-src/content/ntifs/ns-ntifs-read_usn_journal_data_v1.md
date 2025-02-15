---
UID: NS:ntifs.READ_USN_JOURNAL_DATA_V1
tech.root: ifsk
title: READ_USN_JOURNAL_DATA_V1
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the READ_USN_JOURNAL_DATA_V1 structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: READ_USN_JOURNAL_DATA_V1, *PREAD_USN_JOURNAL_DATA_V1
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
 - READ_USN_JOURNAL_DATA_V1
 - PREAD_USN_JOURNAL_DATA_V1
f1_keywords:
 - READ_USN_JOURNAL_DATA_V1
 - ntifs/READ_USN_JOURNAL_DATA_V1
 - PREAD_USN_JOURNAL_DATA_V1
 - ntifs/PREAD_USN_JOURNAL_DATA_V1
dev_langs:
 - c++
helpviewer_keywords:
 - READ_USN_JOURNAL_DATA_V1
---

## -description

The **READ_USN_JOURNAL_DATA_V1** structure contains information defining a set of update sequence number (USN) change journal records to return to the calling process. It is used by the [**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md) and [**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md) control codes. Prior to Windows 8 and Windows Server 2012 this structure was named **READ_USN_JOURNAL_DATA**. Windows Server 2012 introduced **READ_USN_JOURNAL_DATA_V1** to support 128-bit file identifiers used by ReFS.

## -struct-fields

### -field StartUsn

See [**READ_USN_JOURNAL_DATA_V0.StartUsn**](ns-ntifs-read_usn_journal_data_v0.md).

### -field ReasonMask

See [**READ_USN_JOURNAL_DATA_V0.ReasonMask**](ns-ntifs-read_usn_journal_data_v0.md).

### -field ReturnOnlyOnClose

See [**READ_USN_JOURNAL_DATA_V0.ReturnOnlyOnClose**](ns-ntifs-read_usn_journal_data_v0.md).

### -field Timeout

See [**READ_USN_JOURNAL_DATA_V0.Timeout**](ns-ntifs-read_usn_journal_data_v0.md).

### -field BytesToWaitFor

See [**READ_USN_JOURNAL_DATA_V0.BytesToWaitFor**](ns-ntifs-read_usn_journal_data_v0.md).

### -field UsnJournalID

See [**READ_USN_JOURNAL_DATA_V0.UsnJournalID**](ns-ntifs-read_usn_journal_data_v0.md).

### -field MinMajorVersion

The minimum major version of the USN record that the caller can accept. This allows the caller to ensure compatibility with the journal format.

### -field MaxMajorVersion

The maximum major version of the USN record that the caller can accept. This ensures that the caller does not receive records in an unexpected format.

## -remarks

## -see-also

[**FSCTL_QUERY_USN_JOURNAL**](ni-ntifs-fsctl_query_usn_journal.md)

[**FSCTL_READ_USN_JOURNAL**](ni-ntifs-fsctl_read_usn_journal.md)
