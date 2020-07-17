---
UID: NS:wdm._KBUGCHECK_TRIAGE_DUMP_DATA
title: _KBUGCHECK_TRIAGE_DUMP_DATA
author: windows-driver-content
description: 
ms.assetid: 661d08be-f322-43ad-939c-8a4441d4d312
ms.author: windowsdriverdev
ms.date: 06/03/2019
keywords: ["_KBUGCHECK_TRIAGE_DUMP_DATA structure"]
f1_keywords:
 - "wdm/_KBUGCHECK_SECONDARY_DUMP_DATA_EX"
 - "_KBUGCHECK_SECONDARY_DUMP_DATA_EX"
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
api_type: 
- HeaderDef
api_location: 
- wdm.h
apiname: 
- _KBUGCHECK_TRIAGE_DUMP_DATA
product: 
- Windows
targetos: Windows
---

# _KBUGCHECK_TRIAGE_DUMP_DATA structure

## -description

The <b>_KBUGCHECK_TRIAGE_DUMP_DATA</b> structure describes dump data used in conjunction with the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine.

## -struct-fields

### -field DataArray

A pointer to a [_KBUGCHECK_TRIAGE_DUMP_DATA](ns-wdm-_ktriage_dump_data_array.md) structure. This is the method the callback uses to provide the triage block data array that it created. 

### -field Flags

Flags which are passed into the callback.

```cpp
KB_TRIAGE_DUMP_DATA_FLAG_BUGCHECK_ACTIVE 0x00000001
```

Indicates the callback is invoked during a bugcheck.  Currently, this flag is expected to always be set.

### -field MaxVirtMemSize

The maximum virtual memory size in bytes the callback is allowed to add to the dump. The cumulative size of the regions described in the data array should not exceed this size.

### -field BugCheckCode

This value informs the callback which bugcheck code that was passed to KeBugcheckEx. The callback routine can use this information to decide whether to add any memory to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field BugCheckParameter1

Bug Check Parameter 1. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter2

Bug Check Parameter 2. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter3

Bug Check Parameter 3. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter4

Bug Check Parameter 4. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

## -remarks

The driver receives a structure of this type as a parameter to its [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine.

From the callback routine, the driver calls the [**KeAddTriageDumpDataBlock**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keaddtriagedumpdatablock) function to modify a dump data array.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
