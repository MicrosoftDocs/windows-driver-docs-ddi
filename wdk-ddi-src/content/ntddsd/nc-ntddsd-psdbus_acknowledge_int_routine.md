---
UID: NC:ntddsd.PSDBUS_ACKNOWLEDGE_INT_ROUTINE
title: PSDBUS_ACKNOWLEDGE_INT_ROUTINE (ntddsd.h)
description: The PSDBUS_ACKNOWLEDGE_INT_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver must call to acknowledge to the bus driver that it has finished processing the interrupt.
old-location: sd\psdbus_acknowledge_int_routine.htm
tech.root: SD
ms.date: 02/15/2018
keywords: ["PSDBUS_ACKNOWLEDGE_INT_ROUTINE callback function"]
ms.keywords: AcknowledgeInterrupt, AcknowledgeInterrupt callback function [Buses], PSDBUS_ACKNOWLEDGE_INT_ROUTINE, PSDBUS_ACKNOWLEDGE_INT_ROUTINE callback, SD.psdbus_acknowledge_int_routine, ntddsd/AcknowledgeInterrupt, sd-rtns_9197189b-4b46-4ab6-aa7b-df880985241b.xml
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
req.irql: <=DISPATCH_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - PSDBUS_ACKNOWLEDGE_INT_ROUTINE
 - ntddsd/PSDBUS_ACKNOWLEDGE_INT_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ntddsd.h
api_name:
 - PSDBUS_ACKNOWLEDGE_INT_ROUTINE
---

# PSDBUS_ACKNOWLEDGE_INT_ROUTINE callback function


## -description

The PSDBUS_ACKNOWLEDGE_INT_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver must call to acknowledge to the bus driver that it has finished processing the interrupt.

## -parameters

### -param Context 

[in]
Contains the interface context that the <a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a> routine returns in the <b>Context</b> member of the <a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a> structure.

## -returns

Returns STATUS_UNSUCCESSFUL if the operation succeeds, or the appropriate error message if the operation fails.

## -remarks

When an SD device asserts an interrupt, the bus driver disables the interrupt that the device asserted to allow the device driver to perform I/O at IRQL <=DISPATCH_LEVEL. When the device driver's callback routine, which is equivalent to an interrupt service routine, finishes clearing the interrupt, it should acknowledge that it has finished interrupt processing so that the bus driver can re-enable the disabled interrupt. 

Traditionally, drivers acknowledge interrupts by simply returning the appropriate value from the interrupt service routine (ISR). When drivers rely on this method, they are constrained to acknowledge interrupts in the order that they receive them. An SD card driver, on the other hand, is <i>not </i>constrained to acknowledge interrupts in the order that they are received. Typically, a driver for an SD card might report several interrupts to the bus driver (see <a href="/windows-hardware/drivers/ddi/ntddsd/nc-ntddsd-sdbus_callback_routine">PSDBUS_CALLBACK_ROUTINE</a>) before acknowledging any of them. Under normal operating conditions, an SD card driver defers acknowledging an interrupt until the interrupt state on the device has cleared.

The caller must be running at IRQL <= DISPATCH_LEVEL when it acknowledges that it has finished processing an interrupt.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a>



<a href="/windows-hardware/drivers/ddi/ntddsd/nf-ntddsd-sdbusopeninterface">SdBusOpenInterface</a>

