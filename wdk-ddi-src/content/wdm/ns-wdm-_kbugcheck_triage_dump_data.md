---
UID: NS:wdm._KBUGCHECK_TRIAGE_DUMP_DATA
title: _KBUGCHECK_TRIAGE_DUMP_DATA
author: windows-driver-content
description: 
ms.assetid: 661d08be-f322-43ad-939c-8a4441d4d312
ms.author: windowsdriverdev
ms.date: 05/09/2019
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

*Out* - A pointer to a [_KBUGCHECK_TRIAGE_DUMP_DATA](ns-wdm-_ktriage_dump_data_array.md) structure. This is the method the callback uses to provide the triage block data array that it created. 

### -field Flags

*In* - A triage dump data flag. Should always be set to:

```cpp
KB_TRIAGE_DUMP_DATA_FLAG_BUGCHECK_ACTIVE 0x00000001
```

### -field MaxVirtMemSize

*In* - The maximum virtual memory size in bytes is the maximum amount of memory the callback is allowed to add to the dump.

### -field BugCheckCode

*In* - Contains a bug check code, which specifies the reason for the bug check. This value informs the callback what the bugcheck code that was passed to KeBugcheckEx was. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field BugCheckParameter1

*In* - Bug Check Parameter 1. The bug check parameters inform the callback what the bugcheck parameters that were passed to KeBugcheckEx were.

### -field BugCheckParameter2

*In* - Bug Check Parameter 2. The bug check parameters inform the callback what the bugcheck parameters that were passed to KeBugcheckEx were.

### -field BugCheckParameter3

*In* - Bug Check Parameter 3. The bug check parameters inform the callback what the bugcheck parameters that were passed to KeBugcheckEx were.

### -field BugCheckParameter4

*In* - Bug Check Parameter 4. The bug check parameters inform the callback what the bugcheck parameters that were passed to KeBugcheckEx were.

## -remarks

For more information about how this structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.