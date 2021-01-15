---
UID: NS:wdm._KBUGCHECK_CALLBACK_RECORD
title: KBUGCHECK_CALLBACK_RECORD
description: 
tech.root: devtest
ms.date: 05/08/2019
keywords: ["KBUGCHECK_CALLBACK_RECORD structure"]
ms.keywords: KBUGCHECK_CALLBACK_RECORD, KBUGCHECK_CALLBACK_RECORD, *PKBUGCHECK_CALLBACK_RECORD,
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
req.typenames: KBUGCHECK_CALLBACK_RECORD, *PKBUGCHECK_CALLBACK_RECORD
targetos: Windows
f1_keywords:
 - _KBUGCHECK_CALLBACK_RECORD
 - wdm/_KBUGCHECK_CALLBACK_RECORD
 - PKBUGCHECK_CALLBACK_RECORD
 - wdm/PKBUGCHECK_CALLBACK_RECORD
 - KBUGCHECK_CALLBACK_RECORD
 - wdm/KBUGCHECK_CALLBACK_RECORD
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _KBUGCHECK_CALLBACK_RECORD
 - PKBUGCHECK_CALLBACK_RECORD
 - KBUGCHECK_CALLBACK_RECORD
product:
 - Windows
---

# KBUGCHECK_CALLBACK_RECORD structure


## -description

The KBUGCHECK_CALLBACK_RECORD structure is an opaque structure that is used by the KeRegisterBugCheckCallback and KeDeregisterBugCheckCallback routines.

## -struct-fields

### -field Entry

### -field CallbackRoutine

### -field Buffer

### -field Length

### -field Component

### -field Checksum

### -field State

The **KBUGCHECK_CALLBACK_RECORD** structure is used for bookkeeping by the KeRegisterBugCheckReasonCallback and KeDeregisterBugCheckReasonCallback routines.

The structure must be allocated in resident memory, such as nonpaged pool. Use the KeInitializeCallbackRecord routine to initialize the structure before using it.

For more information about how this structure is used, see <a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

