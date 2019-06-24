---
UID: NS:wdm._KBUGCHECK_REMOVE_PAGES
title: KBUGCHECK_REMOVE_PAGES
author: windows-driver-content
description: 
tech.root:
ms.assetid: 787a0ffc-e5fd-4416-915c-3fc46ebb8bf4
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
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
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wdm.h
api_name: 
 - KBUGCHECK_REMOVE_PAGES
product: 
 - Windows
targetos: Windows
---

# KBUGCHECK_REMOVE_PAGES structure

## -description

The <b>KBUGCHECK_REMOVE_PAGES</b> structure describes one or more pages of driver-supplied data to be removed by a [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine from the crash dump file. 


## -struct-fields

### -field Context

Contains private context data for the exclusive use of the callback routine. The callback routine can set this member to any value. Typically, if the callback routine needs to be called more than one time, the routine sets this member to point to a driver-supplied buffer during the initial call. During subsequent calls, the callback routine can read the previous contents of this buffer and update its contents. Before the initial call to the callback routine, <b>Context</b> is <b>NULL</b>.

### -field Flags

Contains flags that describe the remove pages request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits: 

#### KB_REMOVE_PAGES_FLAG_VIRTUAL_ADDRESS

#### KB_REMOVE_PAGES_FLAG_PHYSICAL_ADDRESS

#### KB_REMOVE_PAGES_FLAG_ADDITIONAL_RANGES_EXIST


### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. The callback routine can use this information to decide whether to remove any pages from the crash dump file. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field Address

Specifies the physical or virtual address of the page or pages that the callback routine requests be removed from the crash dump file.

### -field Count

Specifies the number of contiguous pages to remove from the crash dump file, starting from the virtual or physical address that is specified by the <b>Address</b> member. If <b>Count</b> > 1 and <b>Address</b> is a virtual address, the pages are contiguous in virtual memory space. If <b>Count</b> > 1 and <b>Address</b> is a physical address, the pages are contiguous in physical memory space. The callback routine can set this member to zero to indicate that it does not need to remove any pages from the crash dump file.


## -remarks

In a call to the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine, the operating system sets the <i>Reason</i> parameter to <b>KbCallbackRemovePages</b>, and sets the <i>ReasonSpecificData</i> parameter to point to a <b>KBUGCHECK_REMOVE_PAGES</b> structure.

