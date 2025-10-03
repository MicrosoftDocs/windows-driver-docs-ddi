---
UID: NS:wdm._KBUGCHECK_REMOVE_PAGES
title: KBUGCHECK_REMOVE_PAGES
description: "Learn more about: KBUGCHECK_REMOVE_PAGES structure"
tech.root: devtest
ms.date: 09/26/2025
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
---

# KBUGCHECK_REMOVE_PAGES structure

## -description

The **KBUGCHECK_REMOVE_PAGES** structure describes one or more pages of driver-supplied data to be removed by a [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](./nc-wdm-kbugcheck_reason_callback_routine.md) callback routine from the crash dump file.

## -struct-fields

### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, **Context** is NULL.

### -field Flags

Contains flags that describe the remove-page request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits:

| Flag | Value | Description |
|------|-------|-------------|
| **KB_REMOVE_PAGES_FLAG_VIRTUAL_ADDRESS** | 0x00000001UL | Indicates the **Address** member contains a virtual address. |
| **KB_REMOVE_PAGES_FLAG_PHYSICAL_ADDRESS** | 0x00000002UL | Indicates the **Address** member contains a physical address. |
| **KB_REMOVE_PAGES_FLAG_ADDITIONAL_RANGES_EXIST** | 0x80000000UL | Indicates that the callback routine requests that it be called again so that it can remove more pages. |

### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field Address

Specifies the physical or virtual address of the page or pages that the callback routine requests be removed from the crash dump file.

### -field Count

Specifies the number of contiguous pages to remove from the crash dump file, starting from the virtual or physical address that is specified by the **Address** member. If **Count** > 1 and **Address** is a virtual address, the pages are contiguous in virtual memory space. If **Count** > 1 and **Address** is a physical address, the pages are contiguous in physical memory space. The callback routine can set this member to zero to indicate that it does not need to remove any pages from the crash dump file.

## -remarks

In a call to the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](nc-wdm-kbugcheck_reason_callback_routine.md) callback routine, the operating system sets the **Reason** parameter to **KbCallbackRemovePages**, and sets the **ReasonSpecificData** parameter to point to a **KBUGCHECK_REMOVE_PAGES** structure.

For more information about bug check callback routines, see [Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine).

## -see-also

[**KBUGCHECK_ADD_PAGES**](ns-wdm-_kbugcheck_add_pages.md)
