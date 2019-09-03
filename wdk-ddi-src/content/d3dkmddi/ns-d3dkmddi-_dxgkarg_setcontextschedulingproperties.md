---
UID: NS:d3dkmddi._DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES
title: _DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES (d3dkmddi.h)
description: Arguments used to set up or modify the scheduling properties for a device context.
ms.assetid: 907e8775-b899-406f-b104-7b5308f7f177
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmddi/_DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES"
ms.keywords: _DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES, DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES,
req.header: d3dkmddi.h
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
req.typenames: DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _DXGKARG_SETCONTEXTSCHEDULINGPROPERTIES structure

## -description

Contains arguments used in the [DxgkddiSetContextSchedulingProperties](nc-d3dkmddi-dxgkddi_setcontextschedulingproperties.md) callback function.

## -struct-fields

### -field hContext

The hardware context to change the priority band of.

### -field priorityBand

The priority band value assigned to this context. Assigning a context to focus and realtime priority bands requires the calling process to have SE_INC_BASE_PRIORITY_NAME privilege.


### -field realtimeBandPriorityLevel

When the context belongs to the realtime scheduling priority band, this value indicates the priority level (0...31) within the realtime band. For all other bands, this value is ignored.

### -field inProcessPriority

The process wide priority value, relative to other contexts of the same priority within the same process. Values range from -7 to +7. The default in process priority value is zero.

### -field quantum

The context quantum value in 100ns units, relative to other contexts of the same priority within the same process.

### -field gracePeriodSamePriority

The grace period value in 100ns units when this context preempts another context of the same priority within the same process.

### -field gracePeriodLowerPriority

The grace period value in 100ns units when this context preempts another context of a lower priority within the same process. **gracePeriodLowerPriority** is typically smaller than **gracePeriodSamePriority**.


## -see-also

[DxgkddiSetContextSchedulingProperties](nc-d3dkmddi-dxgkddi_setcontextschedulingproperties.md)
