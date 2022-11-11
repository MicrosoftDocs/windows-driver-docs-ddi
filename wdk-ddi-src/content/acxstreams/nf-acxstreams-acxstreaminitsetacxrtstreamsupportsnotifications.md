---
UID: NF:acxstreams.AcxStreamInitSetAcxRtStreamSupportsNotifications
tech.root: audio
title: AcxStreamInitSetAcxRtStreamSupportsNotifications
ms.date: 11/09/2022
targetos: Windows
description: The AcxStreamInitSetAcxRtStreamSupportsNotifications function is used to indicate that buffer notifications are supported.
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
 - AcxStreamInitSetAcxRtStreamSupportsNotifications
f1_keywords:
 - AcxStreamInitSetAcxRtStreamSupportsNotifications
 - acxstreams/AcxStreamInitSetAcxRtStreamSupportsNotifications
dev_langs:
 - c++
---

## -description

The **AcxStreamInitSetAcxRtStreamSupportsNotifications** function is used to indicate that buffer notifications are supported.

## -parameters

### -param StreamInit [in]

Address of a ACXSTREAM_INIT object used to define the stream initialization parameters. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Buffer notifications are supported.
    //
    AcxStreamInitSetAcxRtStreamSupportsNotifications(StreamInit);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
