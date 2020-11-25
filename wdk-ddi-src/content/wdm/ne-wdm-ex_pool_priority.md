---
UID: NE:wdm._EX_POOL_PRIORITY
title: EX_POOL_PRIORITY
ms.date: 03/01/2020
tech.root: 
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _EX_POOL_PRIORITY
 - EX_POOL_PRIORITY
f1_keywords:
 - _EX_POOL_PRIORITY
 - wdm/_EX_POOL_PRIORITY
 - EX_POOL_PRIORITY
 - wdm/EX_POOL_PRIORITY
dev_langs:
 - c++
---

## -description

Specifies the priority of a pool memory allocation request.

## -enum-fields

### -field LowPoolPriority

This setting indicates that it is acceptable to the driver for the mapping request to fail if the system is low on resources.  For example, this could be for a non-critical network connection where the driver can handle the failure case when system resources are close to being depleted.

### -field LowPoolPrioritySpecialPoolOverrun

### -field LowPoolPrioritySpecialPoolUnderrun

### -field NormalPoolPriority

Indicates that it is acceptable to the driver for the mapping request to fail if the system is very low on resources.  For example, this could be for a non-critical local filesystem request.

### -field NormalPoolPrioritySpecialPoolOverrun

### -field NormalPoolPrioritySpecialPoolUnderrun

### -field HighPoolPriority

Should be used when it is unacceptable to the driver for the mapping request to fail unless the system is out of resources. An example of this would be the paging file path in a driver.

### -field HighPoolPrioritySpecialPoolOverrun

### -field HighPoolPrioritySpecialPoolUnderrun

## -syntax

```cpp
typedef _Enum_is_bitflag_ enum _EX_POOL_PRIORITY {
    LowPoolPriority,
    LowPoolPrioritySpecialPoolOverrun = 8,
    LowPoolPrioritySpecialPoolUnderrun = 9,
    NormalPoolPriority = 16,
    NormalPoolPrioritySpecialPoolOverrun = 24,
    NormalPoolPrioritySpecialPoolUnderrun = 25,
    HighPoolPriority = 32,
    HighPoolPrioritySpecialPoolOverrun = 40,
    HighPoolPrioritySpecialPoolUnderrun = 41
} EX_POOL_PRIORITY;
```

## -remarks

The **SpecialPool** settings can be used to bound the allocation at a page beginning or end.Use this option only on systems being debugged as the memory cost is expensive.

## -see-also

[**ExAllocatePoolPriorityZero**](nf-wdm-exallocatepoolpriorityzero.md)

