---
UID: NF:acxstreams.ACX_RTPACKET_INIT
tech.root: audio
title: ACX_RTPACKET_INIT
ms.date: 07/28/2022
targetos: Windows
description: ACX_RTPACKET_INIT initializes the ACX RT packet structure. This function is located in the acxstreams header.
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
 - ACX_RTPACKET_INIT
f1_keywords:
 - ACX_RTPACKET_INIT
 - acxstreams/ACX_RTPACKET_INIT
dev_langs:
 - c++
---

## -description

The **ACX_RTPACKET_INIT** function initializes the ACX RT packet structure.

## -parameters

### -param RtPacket

An [ACX_RTPACKET](ns-acxstreams-acx_rtpacket.md) structure.
 
## -remarks

### Example

```cpp
    packets = (PACX_RTPACKET)ExAllocatePool2(POOL_FLAG_NON_PAGED, packetsSize, DRIVER_TAG);
    RETURN_NTSTATUS_IF_TRUE(!packets, STATUS_NO_MEMORY);
    
    ...

        ACX_RTPACKET_INIT(&packets[i]);
```

## -see-also

- [acxstreams.h header](index.md)
