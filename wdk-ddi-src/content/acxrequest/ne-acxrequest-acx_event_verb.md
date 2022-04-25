---
UID: NE:acxrequest._ACX_EVENT_VERB
tech.root: audio
title: ACX_EVENT_VERB
ms.date: 02/07/2022
targetos: Windows
description: The ACX_EVENT_VERB enumeration describes the type of verb support that will be available.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_EVENT_VERB
 - PACX_EVENT_VERB
 - ACX_EVENT_VERB
f1_keywords:
 - _ACX_EVENT_VERB
 - acxrequest/_ACX_EVENT_VERB
 - PACX_EVENT_VERB
 - acxrequest/PACX_EVENT_VERB
 - ACX_EVENT_VERB
 - acxrequest/ACX_EVENT_VERB
dev_langs:
 - c++
---

## -description

The **ACX_EVENT_VERB** enumeration describes the type of verb support that will be available.

## -enum-fields

### -field AcxEventVerbNone

No verb support.

### -field AcxEventVerbEnable

Verb Support is enabled.

### -field AcxEventVerbDisable

Verb Support is disabled.

### -field AcxEventVerbBasicSupport

Basic Verb support is available.

### -field AcxEventVerbSetSupport

Event Verb support is available.

### -field AcxEventVerbMax

TBD - For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

```cpp
            //
            // Format and send the request. 
            //
            ACX_REQUEST_PARAMETERS_INIT_METHOD(
                &params,
                methodsTests[i].MethodSet,
                methodsTests[i].MethodId,
                AcxMethodVerbSend,
                AcxItemTypeCircuit,
                AcxItemIdNone,
                &arg, sizeof(arg),      // Args & size
                &result, sizeof(result) // Result & size
                );
```

## -see-also

- [acxrequest.h header](index.md)

TBD - Please review this topic