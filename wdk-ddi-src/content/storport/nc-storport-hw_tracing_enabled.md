---
UID: NC:storport.HW_TRACING_ENABLED
title: HW_TRACING_ENABLED (storport.h)
description: The HwStorTracingEnabled callback routine enables the Storport to notify a miniport that event tracing is enabled.
old-location: storage\hwstortracingenabled.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_TRACING_ENABLED callback function"]
ms.keywords: HW_TRACING_ENABLED, HwStorTracingEnabled, HwStorTracingEnabled routine [Storage Devices], storage.hwstortracingenabled, storport/HwStorTracingEnabled
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_TRACING_ENABLED
 - storport/HW_TRACING_ENABLED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HwStorTracingEnabled
---

# HW_TRACING_ENABLED callback function

## -description

The **HwStorTracingEnabled** callback routine enables the Storport to notify a miniport that event tracing is enabled.

## -parameters

### -param HwDeviceExtension

### -param Enabled

[in] True to enable tracing in the miniport. Otherwise, false.

#### - DeviceExtension

[in] A pointer to the miniport driver's per-HBA storage area.

## -remarks

The name *HwStorTracingEnabled* is placeholder text for the actual routine name. The actual prototype of this routine is defined in *Storport.h* as follows:

```cpp
typedef
VOID
HW_TRACING_ENABLED (
    _In_ PVOID HwDeviceExtension,
    _In_ BOOLEAN Enabled
    );
```

## -see-also

[**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md)
