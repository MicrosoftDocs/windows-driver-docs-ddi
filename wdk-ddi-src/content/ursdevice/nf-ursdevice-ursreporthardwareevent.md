---
UID: NF:ursdevice.UrsReportHardwareEvent
title: UrsReportHardwareEvent function (ursdevice.h)
description: Notifies the USB dual-role class extension about a new hardware event.
old-location: buses\ursreporthardwareevent.htm
tech.root: usbref
ms.date: 01/19/2022
keywords: ["UrsReportHardwareEvent function"]
ms.keywords: UrsReportHardwareEvent, UrsReportHardwareEvent function [Buses], buses.ursreporthardwareevent, ursdevice/UrsReportHardwareEvent
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: HIGH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UrsReportHardwareEvent
 - ursdevice/UrsReportHardwareEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Urscxstub.lib
 - Urscxstub.dll
api_name:
 - UrsReportHardwareEvent
---

# UrsReportHardwareEvent function

## -description

Notifies the USB dual-role class extension about a new hardware event.

## -parameters

### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param HardwareEvent [in]

A [URS_HARDWARE_EVENT](../urstypes/ne-urstypes-_urs_hardware_event.md)-type value that indicates the type of event that occurred.

## -remarks

Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling [UrsSetHardwareEventSupport](nf-ursdevice-urssethardwareeventsupport.md).

The client driver cannot pass **UrsHardwareEventNone** as the *HardwareEvent* parameter value. That value is reserved for internal use.

The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the [EvtInterruptIsr](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr.md) callback, the driver reads the ID-pin state and reports the event to the class extension by calling this method.

## -see-also

- [WdfDeviceCreate](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md)
- [URS_HARDWARE_EVENT](../urstypes/ne-urstypes-_urs_hardware_event.md)
- [UrsSetHardwareEventSupport](nf-ursdevice-urssethardwareeventsupport.md)
- [EvtInterruptIsr](../wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr.md)
