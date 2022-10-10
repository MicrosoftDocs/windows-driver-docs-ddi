---
UID: NS:ntddsd._SDBUS_INTERFACE_PARAMETERS
tech.root: sd
title: SDBUS_INTERFACE_PARAMETERS
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the SDBUS_INTERFACE_PARAMETERS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddsd.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SDBUS_INTERFACE_PARAMETERS, *PSDBUS_INTERFACE_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddsd.h
api_name:
 - _SDBUS_INTERFACE_PARAMETERS
 - PSDBUS_INTERFACE_PARAMETERS
 - SDBUS_INTERFACE_PARAMETERS
f1_keywords:
 - _SDBUS_INTERFACE_PARAMETERS
 - ntddsd/_SDBUS_INTERFACE_PARAMETERS
 - PSDBUS_INTERFACE_PARAMETERS
 - ntddsd/PSDBUS_INTERFACE_PARAMETERS
 - SDBUS_INTERFACE_PARAMETERS
 - ntddsd/SDBUS_INTERFACE_PARAMETERS
dev_langs:
 - c++
helpviewer_keywords:
 - _SDBUS_INTERFACE_PARAMETERS
---

## -description

The SDBUS\_INTERFACE\_PARAMETERS structure contains the information necessary to initialize a Secure Digital (SD) card bus interface.

## -struct-fields

### -field Size

Indicates the size, in bytes, of this structure, including the area pointed to by the **CallbackRoutineContext** member.

### -field SdioFlags

Reserved.

### -field TargetObject

Pointer to the next lower device object in the device stack. The caller should initialize this member to point to the device object below the caller's device object in the device stack.

### -field DeviceGeneratesInterrupts

Indicates, when **TRUE**, that the SD device generates interrupts. If **FALSE**, the device does not generate interrupts.

### -field CallbackAtDpcLevel

Indicates, when **TRUE**, that the callback routine must run at DISPATCH\_LEVEL. If **FALSE**, the callback must run at PASSIVE\_LEVEL. A device driver can often lower the latency of interrupt delivery by setting this member to **TRUE**; however, drivers that set this value to **TRUE** must be able to run at both PASSIVE\_LEVEL and DISPATCH\_LEVEL.

### -field CallbackRoutine

Pointer to a callback routine of type [**PSDBUS\_CALLBACK\_ROUTINE**](nc-ntddsd-sdbus_callback_routine.md) that the bus driver calls when a device interrupt occurs. If **DeviceGeneratesInterrupts** is not set to **TRUE**, then the bus driver ignores the value in this member.

### -field CallbackRoutineContext

Pointer to the context information that the bus driver should pass to the callback routine when it dispatches a device interrupt.

## -remarks

An SD device driver that obtains a bus interface instance from the bus driver must initialize the interface. After obtaining an interface instance, the device driver passes the data in the SDBUS\_INTERFACE\_PARAMETERS structure to the routine pointed to by the **InitializeInterface** member of the [**SDBUS\_INTERFACE\_STANDARD**](ns-ntddsd-sdbus_interface_standard.md) structure.

## -see-also

[**PSDBUS\_CALLBACK\_ROUTINE**](nc-ntddsd-sdbus_callback_routine.md)

[**SDBUS\_INTERFACE\_STANDARD**](ns-ntddsd-sdbus_interface_standard.md)
