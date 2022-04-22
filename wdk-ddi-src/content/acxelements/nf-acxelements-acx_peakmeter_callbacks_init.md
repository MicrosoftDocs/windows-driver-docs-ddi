---
UID: NF:acxelements.ACX_PEAKMETER_CALLBACKS_INIT
tech.root: audio 
title: ACX_PEAKMETER_CALLBACKS_INIT
ms.date: 09/21/2021
targetos: Windows
description: The ACX_PEAKMETER_CALLBACKS_INIT function initializes a ACX_PEAKMETER_CALLBACKS structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - acxelements.h
api_name:
 - ACX_PEAKMETER_CALLBACKS_INIT
f1_keywords:
 - ACX_PEAKMETER_CALLBACKS_INIT
 - acxelements/ACX_PEAKMETER_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_PEAKMETER_CALLBACKS_INIT function initializes a [ACX_PEAKMETER_CALLBACKS structure](ns-acxelements-acx_peakmeter_callbacks.md). 

## -parameters

### -param Callbacks

A pointer to an initialized [ACX_PEAKMETER_CALLBACKS structure](ns-acxelements-acx_peakmeter_callbacks.md). 

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_PEAKMETER_CALLBACKS         peakmeterCallbacks;
    ACX_PEAKMETER_CALLBACKS_INIT(&peakmeterCallbacks);
```

## -see-also

[acxelements.h header](index.md)

READY2GO

