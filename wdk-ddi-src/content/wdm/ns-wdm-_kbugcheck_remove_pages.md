---
UID: NS:wdm._KBUGCHECK_REMOVE_PAGES
title: _KBUGCHECK_REMOVE_PAGES
description: 
tech.root: devtest
ms.date: 05/08/2019
keywords: ["KBUGCHECK_REMOVE_PAGES structure"]
ms.keywords: KBUGCHECK_REMOVE_PAGES, KBUGCHECK_REMOVE_PAGES, *PKBUGCHECK_REMOVE_PAGES,
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
req.typenames: KBUGCHECK_REMOVE_PAGES, *PKBUGCHECK_REMOVE_PAGES
targetos: Windows
f1_keywords:
 - _KBUGCHECK_REMOVE_PAGES
 - wdm/_KBUGCHECK_REMOVE_PAGES
 - PKBUGCHECK_REMOVE_PAGES
 - wdm/PKBUGCHECK_REMOVE_PAGES
 - KBUGCHECK_REMOVE_PAGES
 - wdm/KBUGCHECK_REMOVE_PAGES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _KBUGCHECK_REMOVE_PAGES
 - PKBUGCHECK_REMOVE_PAGES
 - KBUGCHECK_REMOVE_PAGES
product:
 - Windows
---

# KBUGCHECK_REMOVE_PAGES structure


## -description

The <b>KBUGCHECK_REMOVE_PAGES</b> structure describes one or more pages of driver-supplied data to be removed by a [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](./nc-wdm-kbugcheck_reason_callback_routine.md) callback routine from the crash dump file.

## -struct-fields

### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, <b>Context</b> is <b>NULL</b>.

### -field Flags

Contains flags that describe the remove-page request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits: 

```cpp
KB_ADD_PAGES_FEATURE_SHIFT       4

KB_REMOVE_PAGES_FEATURE_SHIFT    4

KB_ADD_PAGES_FEATURE_MASK        (0xF << KB_ADD_PAGES_FEATURE_SHIFT)

KB_REMOVE_PAGES_FEATURE_MASK     (0xF << (KB_ADD_PAGES_FEATURE_SHIFT + KB_REMOVE_PAGES_FEATURE_SHIFT))
```

### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field Address

Specifies the physical or virtual address of the page or pages that the callback routine requests be removed from the crash dump file.

### -field Count

Specifies the number of contiguous pages to remove from the crash dump file, starting from the virtual or physical address that is specified by the <b>Address</b> member. If <b>Count</b> > 1 and <b>Address</b> is a virtual address, the pages are contiguous in virtual memory space. If <b>Count</b> > 1 and <b>Address</b> is a physical address, the pages are contiguous in physical memory space. The callback routine can set this member to zero to indicate that it does not need to remove any pages from the crash dump file.

## -remarks

In a call to the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](./nc-wdm-kbugcheck_reason_callback_routine.md) callback routine, the operating system sets the <i>Reason</i> parameter to <b>KbCallbackRemovePages</b>, and sets the <i>ReasonSpecificData</i> parameter to point to a <b>KBUGCHECK_REMOVE_PAGES</b> structure.

For more information about bug check callback routines, see <a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

