---
UID: NS:wdm._KBUGCHECK_SECONDARY_DUMP_DATA_EX
title: _KBUGCHECK_SECONDARY_DUMP_DATA_EX
author: windows-driver-content
description: 
tech.root:
ms.assetid: 85ff55ca-e626-4214-9844-2eac78b9dcc5
ms.author: windowsdriverdev
ms.date: 06/03/2019
ms.topic: struct
f1_keywords:
 - "wdm/_KBUGCHECK_SECONDARY_DUMP_DATA_EX"
ms.keywords: KBUGCHECK_SECONDARY_DUMP_DATA_EX, KBUGCHECK_SECONDARY_DUMP_DATA_EX, *PKBUGCHECK_SECONDARY_DUMP_DATA_EX, 
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
req.typenames: KBUGCHECK_SECONDARY_DUMP_DATA_EX, *PKBUGCHECK_SECONDARY_DUMP_DATA_EX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wdm.h
api_name: 
- _KBUGCHECK_SECONDARY_DUMP_DATA_EX
product: 
- Windows
targetos: Windows
---

# _KBUGCHECK_SECONDARY_DUMP_DATA_EX structure

## -description

The <b>KBUGCHECK_SECONDARY_DUMP_DATA_EX</b> structure describes multipart data to be written by [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine to the crash dump file.


## -struct-fields

### -field InBuffer

Pointer to a buffer that is allocated by the system.
 
### -field InBufferLength

Specifies the size of the buffer, in bytes, specified by the <b>InBuffer</b> member.
 
### -field MaximumAllowed

Specifies the maximum amount of data that the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) routine can write to the crash dump file.

### -field Guid

Specifies a GUID that identifies the driver's crash dump data. (Drivers must use unique GUIDs to mark their crash dump data. Use the GuidGen.exe tool to generate GUIDs for your driver.

### -field OutBuffer

Pointer to the buffer where the driver writes its crash dump data, or <b>NULL</b>.

### -field OutBufferLength

Specifies the size of the buffer, in bytes, that was specified by the <b>OutBuffer</b> member.

### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, Context is NULL.

### -field Flags

Contains flags that describe the add-page request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits: 

#### KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS

Indicates that the <b>Address</b> member contains a virtual address.

#### KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS

Indicates that the <b>Address</b> member contains a physical address.

#### KB_ADD_PAGES_FLAG_ADDITIONAL_RANGES_EXIST

Indicates that the callback routine requests that it be called again so that it can add more pages.

The callback routine must set either the KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS flag or the KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS flag, but not both. On entry to the callback routine, <b>Flags</b> is initialized to zero.
 
### -field DumpType

One of the following dump types.

```cpp
    DUMP_TYPE_INVALID           = -1,
    DUMP_TYPE_UNKNOWN           = 0,
    DUMP_TYPE_FULL              = 1,
    DUMP_TYPE_SUMMARY           = 2,
    DUMP_TYPE_HEADER            = 3,
    DUMP_TYPE_TRIAGE            = 4,
    DUMP_TYPE_BITMAP_FULL       = 5,
    DUMP_TYPE_BITMAP_KERNEL     = 6,
    DUMP_TYPE_AUTOMATIC         = 7
```
 
### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.
 
### -field BugCheckParameter1

Bug Check Parameter 1. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter2

Bug Check Parameter 2. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter3

Bug Check Parameter 3. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.

### -field BugCheckParameter4

Bug Check Parameter 4. The bug check parameters inform the callback the bugcheck parameters that were passed to KeBugcheckEx.
 
## -remarks

For more information about bug check callback routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
[*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine)
