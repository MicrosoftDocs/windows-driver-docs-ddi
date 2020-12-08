---
UID: NC:ntddsd.SDBUS_CALLBACK_ROUTINE
title: SDBUS_CALLBACK_ROUTINE (ntddsd.h)
description: The PSDBUS_CALLBACK_ROUTINE prototype declares the Secure Digital (SD) driver callback routine that the SD bus driver uses to report device interrupts to the driver.
old-location: sd\psdbus_callback_routine.htm
tech.root: SD
ms.date: 02/15/2018
keywords: ["SDBUS_CALLBACK_ROUTINE callback function"]
ms.keywords: SD.psdbus_callback_routine, SDBUS_CALLBACK_ROUTINE, SDBUS_CALLBACK_ROUTINE callback, SdBusCallbackRoutine, SdBusCallbackRoutine callback function [Buses], ntddsd/SdBusCallbackRoutine, sd-rtns_a51040c8-723c-45ae-9e3b-15ef2baca85b.xml
req.header: ntddsd.h
req.include-header: Ntddsd.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - SDBUS_CALLBACK_ROUTINE
 - ntddsd/SDBUS_CALLBACK_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddsd.h
api_name:
 - SdBusCallbackRoutine
---

# SDBUS_CALLBACK_ROUTINE callback function


## -description

The PSDBUS_CALLBACK_ROUTINE prototype declares the Secure Digital (SD) driver callback routine that the SD bus driver uses to report device interrupts to the driver.

## -parameters

### -param CallbackRoutineContext 

[in]
Pointer to the context information that the bus driver passes to the callback routine. The device driver supplies the bus driver with this information when it initializes the SD bus interface.

### -param InterruptType 

[in]
Must be set to SDBUS_INTTYPE_DEVICE.

## -remarks

When an SD device driver initializes an instance of the SD bus interface, it loads the <b>CallbackRoutine</b> member of the <a href="/previous-versions/windows/hardware/drivers/ff537919(v=vs.85)">SDBUS_INTERFACE_PARAMETERS</a> structure with a pointer to PSDBUS_CALLBACK_ROUTINE.

The bus driver calls the SD card driver's callback routine whenever the card indicates an interrupt. The callback routine must send the appropriate device commands to handle and clear the interrupt on the card. After it completes the series of I/O operations, the SD card driver should acknowledge the interrupt. For more information about how SD card drivers acknowledge interrupts, see <a href="/windows-hardware/drivers/ddi/ntddsd/nc-ntddsd-psdbus_acknowledge_int_routine">PSDBUS_ACKNOWLEDGE_INT_ROUTINE</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff537919(v=vs.85)">SDBUS_INTERFACE_PARAMETERS</a>
