---
UID: NS:wdm._KBUGCHECK_ADD_PAGES
title: KBUGCHECK_ADD_PAGES (wdm.h)
description: The KBUGCHECK_ADD_PAGES structure describes one or more pages of driver-supplied data to be written by a KbCallbackAddPages callback routine to the crash dump file.
tech.root: kernel
ms.date: 09/26/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: KBUGCHECK_ADD_PAGES, *PKBUGCHECK_ADD_PAGES
f1_keywords:
 - _KBUGCHECK_ADD_PAGES
 - wdm/_KBUGCHECK_ADD_PAGES
 - PKBUGCHECK_ADD_PAGES
 - wdm/PKBUGCHECK_ADD_PAGES
 - KBUGCHECK_ADD_PAGES
 - wdm/KBUGCHECK_ADD_PAGES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _KBUGCHECK_ADD_PAGES
 - PKBUGCHECK_ADD_PAGES
 - KBUGCHECK_ADD_PAGES
---

# KBUGCHECK_ADD_PAGES structure

## -description

The **KBUGCHECK_ADD_PAGES** structure describes one or more pages of driver-supplied data to be written by a [KBUGCHECK_REASON_CALLBACK_ROUTINE](nc-wdm-kbugcheck_reason_callback_routine.md) callback function to the crash dump file.

## -struct-fields

### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, **Context** is NULL.

### -field Flags

Contains flags that describe the add-page request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits:

| Flag | Description |
|------|-------------|
| **KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS** | Indicates that the **Address** member contains a virtual address. |
| **KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS** | Indicates that the **Address** member contains a physical address. |
| **KB_ADD_PAGES_FLAG_ADDITIONAL_RANGES_EXIST** | Indicates that the callback routine requests that it be called again so that it can add more pages. |

The callback routine must set either the **KB_ADD_PAGES_FLAG_VIRTUAL_ADDRESS** flag or the **KB_ADD_PAGES_FLAG_PHYSICAL_ADDRESS** flag, but not both. On entry to the callback routine, **Flags** is initialized to zero.

### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to add any pages to the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field Address

Specifies the physical or virtual address of the page or pages that the callback routine requests be added to the crash dump file.

### -field Count

Specifies the number of contiguous pages to add to the crash dump file, starting from the virtual or physical address that is specified by the **Address** member. If **Count** > 1 and **Address** is a virtual address, the pages are contiguous in virtual memory space. If **Count** > 1 and **Address** is a physical address, the pages are contiguous in physical memory space. The callback routine can set this member to zero to indicate that it does not need to add any pages to the crash dump file.

## -remarks

In a call to the **KbCallbackAddPages** callback routine, the operating system sets the **Reason** parameter to **KbCallbackAddPages**, and sets the **ReasonSpecificData** parameter to point to a **KBUGCHECK_ADD_PAGES** structure.

For more information about how this structure is used, see [Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine) and [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](nc-wdm-kbugcheck_reason_callback_routine.md) callback function.

## -see-also

[**KBUGCHECK_REMOVE_PAGES**](ns-wdm-_kbugcheck_remove_pages.md)
