---
UID: NF:acxstreams.DEFINE_ACXDRMRIGHTS_DEFAULT
tech.root: audio
title: DEFINE_ACXDRMRIGHTS_DEFAULT
ms.date: 07/09/2021
targetos: Windows
description: This macro provides the following default for DRM rights TBD???
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
 - DEFINE_ACXDRMRIGHTS_DEFAULT
f1_keywords:
 - DEFINE_ACXDRMRIGHTS_DEFAULT
 - acxstreams/DEFINE_ACXDRMRIGHTS_DEFAULT
dev_langs:
 - c++
---

## -description

This macro provides the following default for DRM rights TBD???

```cpp
#define DEFINE_ACXDRMRIGHTS_DEFAULT(DrmRights) const ACXDRMRIGHTS DrmRights = {FALSE, 0, FALSE}
```

## -parameters

### -param DrmRights

Specifies the DRM content rights that are assigned to the stream that is identified by ContentId. This parameter is a pointer to a [ACXDRMRIGHTS structure](ns-acxstreams-acxdrmrights.md).

## -remarks

### Example

TBD - no sample driver code found

Example usage is shown below.

```cpp

```



## -see-also

[acxstreams.h header](index.md)

