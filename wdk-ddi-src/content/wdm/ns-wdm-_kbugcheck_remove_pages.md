---
UID: NS:wdm._KBUGCHECK_REMOVE_PAGES
title: KBUGCHECK_REMOVE_PAGES
author: windows-driver-content
description: 
tech.root:
ms.assetid: 3b597044-e02a-48ed-9172-83644f0ef44e
ms.author: windowsdriverdev
ms.date: 05/08/2019
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

## -struct-fields

### -field Context
Private context for callback use.

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

Information pending.

### -field Count

Information pending.

## -remarks

For more information about how this structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
