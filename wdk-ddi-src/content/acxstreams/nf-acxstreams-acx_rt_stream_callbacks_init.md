---
UID: NF:acxstreams.ACX_RT_STREAM_CALLBACKS_INIT
tech.root: audio
title: ACX_RT_STREAM_CALLBACKS_INIT
ms.date: 06/23/2021
targetos: Windows
description: The ACX_RT_STREAM_CALLBACKS_INIT function method initializes the ACX RT stream callbacks.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - ACX_RT_STREAM_CALLBACKS_INIT
f1_keywords:
 - ACX_RT_STREAM_CALLBACKS_INIT
 - acxstreams/ACX_RT_STREAM_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_RT_STREAM_CALLBACKS_INIT function initializes the ACX RT stream callbacks.

## -parameters

### -param Callbacks

An [ACX_RT_STREAM_CALLBACKS](ns-acxstreams-acx_rt_stream_callbacks.md) structure. 

## -remarks

### Example

```cpp
    //
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
```

## -see-also

- [acxstreams.h header](index.md)

READY2GO