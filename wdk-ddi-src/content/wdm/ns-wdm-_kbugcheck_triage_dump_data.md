---
UID: NS:wdm._KBUGCHECK_TRIAGE_DUMP_DATA
title: _KBUGCHECK_TRIAGE_DUMP_DATA
author: windows-driver-content
description: 
ms.assetid: 661d08be-f322-43ad-939c-8a4441d4d312
ms.author: windowsdriverdev
ms.date: 05/08/2019
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _KBUGCHECK_TRIAGE_DUMP_DATA, KBUGCHECK_TRIAGE_DUMP_DATA, *PKBUGCHECK_TRIAGE_DUMP_DATA, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: KBUGCHECK_TRIAGE_DUMP_DATA, *PKBUGCHECK_TRIAGE_DUMP_DATA
topictype: 
- apiref
apitype: 
- HeaderDef
apilocation: 
- wdm.h
apiname: 
-_KBUGCHECK_TRIAGE_DUMP_DATA
product: 
- Windows
targetos: Windows
---

# _KBUGCHECK_TRIAGE_DUMP_DATA structure

## -description

## -struct-fields

### -field DataArray

A pointer to a [_KBUGCHECK_TRIAGE_DUMP_DATA](ns-wdm-_ktriage_dump_data_array.md) structure.

### -field Flags

A triage dump data flag such as:

```cpp
KB_TRIAGE_DUMP_DATA_FLAG_BUGCHECK_ACTIVE 0x00000001
```

### -field MaxVirtMemSize

The maximum virtual memory size (in bytes?).

### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.
 
### -field BugCheckParameter1

Bug Check Parameter 1. This value is set (or read) by ___________???

### -field BugCheckParameter2

Bug Check Parameter 2. This value is set (or read) by ___________???

### -field BugCheckParameter3

Bug Check Parameter 3. This value is set (or read) by ___________???

### -field BugCheckParameter4

Bug Check Parameter 4. This value is set (or read) by ___________???

## -remarks

For more information about how this structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.