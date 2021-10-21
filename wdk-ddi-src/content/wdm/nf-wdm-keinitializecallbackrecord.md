---
UID: NF:wdm.KeInitializeCallbackRecord
tech.root: 
title: KeInitializeCallbackRecord
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: KeInitializeCallbackRecord"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KeInitializeCallbackRecord
f1_keywords:
 - KeInitializeCallbackRecord
 - wdm/KeInitializeCallbackRecord
dev_langs:
 - c++
---

## -description

The **KeInitializeCallbackRecord** macro initializes a [**KBUGCHECK_CALLBACK_RECORD**](/windows-hardware/drivers/kernel/eprocess) or [**KBUGCHECK_REASON_CALLBACK_RECORD**](/windows-hardware/drivers/kernel/eprocess) structure.

## -parameters

### -param CallbackRecord [in]


Pointer to either a **KBUGCHECK_CALLBACK_RECORD** or a **KBUGCHECK_REASON_CALLBACK_RECORD** structure. The structure must be in resident memory, such as nonpaged pool.

## -remarks

