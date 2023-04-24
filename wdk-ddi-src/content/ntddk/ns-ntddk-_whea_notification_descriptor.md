---
UID: NS:ntddk._WHEA_NOTIFICATION_DESCRIPTOR
title: WHEA_NOTIFICATION_DESCRIPTOR (ntddk.h)
description: The WHEA_NOTIFICATION_DESCRIPTOR structure describes the notification mechanism that is used by an error source.
tech.root: whea
ms.date: 01/11/2023
keywords: ["WHEA_NOTIFICATION_DESCRIPTOR structure"]
ms.keywords: "*PWHEA_NOTIFICATION_DESCRIPTOR, AsUSHORT, ErrorThresholdRW, ErrorThresholdWindowRW, PollIntervalRW, Reserved, SwitchToPollingThresholdRW, SwitchToPollingWindowRW, WHEA_NOTIFICATION_DESCRIPTOR, WHEA_NOTIFICATION_DESCRIPTOR structure [WHEA Drivers and Applications], WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT, WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT, WHEA_NOTIFICATION_TYPE_NMI, WHEA_NOTIFICATION_TYPE_POLLED, WHEA_NOTIFICATION_TYPE_SCI, _WHEA_NOTIFICATION_DESCRIPTOR, ntddk/WHEA_NOTIFICATION_DESCRIPTOR, whea.whea_notification_descriptor, whearef_c2a5ab66-2598-447b-8f5b-d6398c55ff1a.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
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
req.typenames: WHEA_NOTIFICATION_DESCRIPTOR, *PWHEA_NOTIFICATION_DESCRIPTOR
f1_keywords:
 - _WHEA_NOTIFICATION_DESCRIPTOR
 - ntddk/_WHEA_NOTIFICATION_DESCRIPTOR
 - PWHEA_NOTIFICATION_DESCRIPTOR
 - ntddk/PWHEA_NOTIFICATION_DESCRIPTOR
 - WHEA_NOTIFICATION_DESCRIPTOR
 - ntddk/WHEA_NOTIFICATION_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - _WHEA_NOTIFICATION_DESCRIPTOR
 - PWHEA_NOTIFICATION_DESCRIPTOR
 - WHEA_NOTIFICATION_DESCRIPTOR
---

## -description

The **WHEA_NOTIFICATION_DESCRIPTOR** structure describes the notification mechanism that is used by an error source.

## -struct-fields

### -field Type

The type of notification mechanism that is used by the error source. This can be one of the following possible values.

| Value | Meaning |
|---|---|
| **WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT** | The error source notifies the LLHEH for the error source by means of an external interrupt. |
| **WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT** | The error source notifies the LLHEH for the error source by means of a local interrupt. |
| **WHEA_NOTIFICATION_TYPE_NMI** | The error source notifies the LLHEH for the error source by means of a nonmaskable interrupt (NMI). |
| **WHEA_NOTIFICATION_TYPE_POLLED** | The low-level hardware error handler (LLHEH)for the error source must periodically poll the error status registers to check for an error condition. |
| **WHEA_NOTIFICATION_TYPE_SCI** | The error source notifies the LLHEH for the error source by means of a service control interrupt (SCI). |

### -field Length

The size, in bytes, of the **WHEA_NOTIFICATION_DESCRIPTOR** structure.

### -field Flags

A WHEA_NOTIFICATION_FLAGS union that indicates which of the members of the **WHEA_NOTIFICATION_DESCRIPTOR** structure can be written to by the operating system. The WHEA_NOTIFICATION_FLAGS union is defined as follows:

```cpp
typedef union _WHEA_NOTIFICATION_FLAGS {
  struct {
    USHORT  PollIntervalRW:1;
    USHORT  SwitchToPollingThresholdRW:1;
    USHORT  SwitchToPollingWindowRW:1;
    USHORT  ErrorThresholdRW:1;
    USHORT  ErrorThresholdWindowRW:1;
    USHORT  Reserved:11;
  };
  USHORT  AsUSHORT;
} WHEA_NOTIFICATION_FLAGS, *PWHEA_NOTIFICATION_FLAGS
```

| Value | Meaning |
|---|---|
| **AsUSHORT** | A USHORT representation of the contents of the WHEA_NOTIFICATION_FLAGS union. |
| **ErrorThresholdRW** | A single bit that indicates that the operating system can write to the **u.***xxx***.ErrorThreshold** members of the WHEA_NOTIFICATION_DESCRIPTOR structure. |
| **ErrorThresholdWindowRW** | A single bit that indicates that the operating system can write to the **u.***xxx***.ErrorThresholdWindow** members of the WHEA_NOTIFICATION_DESCRIPTOR structure. |
| **PollIntervalRW** | A single bit that indicates that the operating system can write to the **u.***xxx***.PollInterval** members of the WHEA_NOTIFICATION_DESCRIPTOR structure. |
| **Reserved** | Reserved for system use. |
| **SwitchToPollingThresholdRW** | A single bit that indicates that the operating system can write to the **u.***xxx***.SwitchToPollingThreshold** members of the WHEA_NOTIFICATION_DESCRIPTOR structure. |
| **SwitchToPollingWindowRW** | A single bit that indicates that the operating system can write to the **u.***xxx***.SwitchToPollingWindow** members of the WHEA_NOTIFICATION_DESCRIPTOR structure. |

### -field u

A union of structures that are specific to each different type of notification mechanism.

### -field u.Polled

A structure that describes the notification mechanism when the **Type** member is set to WHEA_NOTIFICATION_TYPE_POLLED.

### -field u.Polled.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition.

### -field u.Interrupt

A structure that describes the notification mechanism when the **Type** member is set to WHEA_NOTIFICATION_TYPE_EXTERNALINTERRUPT.

### -field u.Interrupt.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.

### -field u.Interrupt.Vector

The interrupt vector for the error source.

### -field u.Interrupt.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the **SwitchToPollingWindow** member before the error source is switched to polling mode.

### -field u.Interrupt.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the **SwitchToPollingThreshold** member must occur before the error source is switched to polling mode.

### -field u.Interrupt.ErrorThreshold

The number of errors that must occur within the time specified by the **ErrorThresholdWindow** member before an error from the error source is processed by the operating system.

### -field u.Interrupt.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the **ErrorThreshold** member must occur before an error from the error source is processed by the operating system.

### -field u.LocalInterrupt

A structure that describes the notification mechanism when the **Type** member is set to WHEA_NOTIFICATION_TYPE_LOCALINTERRUPT.

### -field u.LocalInterrupt.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.

### -field u.LocalInterrupt.Vector

The interrupt vector for the error source.

### -field u.LocalInterrupt.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the **SwitchToPollingWindow** member before the error source is switched to polling mode.

### -field u.LocalInterrupt.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the **SwitchToPollingThreshold** member must occur before the error source is switched to polling mode.

### -field u.LocalInterrupt.ErrorThreshold

The number of errors that must occur within the time specified by the **ErrorThresholdWindow** member before an error from the error source is processed by the operating system.

### -field u.LocalInterrupt.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the **ErrorThreshold** member must occur before an error from the error source is processed by the operating system.

### -field u.Sci

 A structure that describes the notification mechanism when the **Type** member is set to WHEA_NOTIFICATION_TYPE_SCI.

### -field u.Sci.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.

### -field u.Sci.Vector

The interrupt vector for the error source.

### -field u.Sci.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the **SwitchToPollingWindow** member before the error source is switched to polling mode.

### -field u.Sci.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the **SwitchToPollingThreshold** member must occur before the error source is switched to polling mode.

### -field u.Sci.ErrorThreshold

The number of errors that must occur within the time specified by the **ErrorThresholdWindow** member before an error from the error source is processed by the operating system.

### -field u.Sci.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the **ErrorThreshold** member must occur before an error from the error source is processed by the operating system.

### -field u.Nmi

A structure that describes the notification mechanism when the **Type** member is set to WHEA_NOTIFICATION_TYPE_NMI.

### -field u.Nmi.PollInterval

The interval, in milliseconds, that the LLHEH for the error source should poll the error status registers to check for an error condition if the error source is switched out of interrupt mode.

### -field u.Nmi.Vector

The interrupt vector for the error source.

### -field u.Nmi.SwitchToPollingThreshold

The number of errors that must occur within the time specified by the **SwitchToPollingWindow** member before the error source is switched to polling mode.

### -field u.Nmi.SwitchToPollingWindow

The window of time, in seconds, in which the number of errors specified by the **SwitchToPollingThreshold** member must occur before the error source is switched to polling mode.

### -field u.Nmi.ErrorThreshold

The number of errors that must occur within the time specified by the **ErrorThresholdWindow** member before an error from the error source is processed by the operating system.

### -field u.Nmi.ErrorThresholdWindow

The window of time, in seconds, in which the number of errors specified by the **ErrorThreshold** member must occur before an error from the error source is processed by the operating system.

### -field u.Sea

### -field u.Sea.PollInterval

### -field u.Sea.Vector

### -field u.Sea.SwitchToPollingThreshold

### -field u.Sea.SwitchToPollingWindow

### -field u.Sea.ErrorThreshold

### -field u.Sea.ErrorThresholdWindow

### -field u.Sei

### -field u.Sei.PollInterval

### -field u.Sei.Vector

### -field u.Sei.SwitchToPollingThreshold

### -field u.Sei.SwitchToPollingWindow

### -field u.Sei.ErrorThreshold

### -field u.Sei.ErrorThresholdWindow

### -field u.Gsiv

### -field u.Gsiv.PollInterval

### -field u.Gsiv.Vector

### -field u.Gsiv.SwitchToPollingThreshold

### -field u.Gsiv.SwitchToPollingWindow

### -field u.Gsiv.ErrorThreshold

### -field u.Gsiv.ErrorThresholdWindow

## -remarks

A **WHEA_NOTIFICATION_DESCRIPTOR** structure is contained within the [**WHEA_GENERIC_ERROR_DESCRIPTOR**](./ns-ntddk-_whea_generic_error_descriptor.md) and [WHEA_XPF_CMC_DESCRIPTOR](./ns-ntddk-_whea_xpf_cmc_descriptor.md) structures.

## -see-also

[**WHEA_GENERIC_ERROR_DESCRIPTOR**](./ns-ntddk-_whea_generic_error_descriptor.md)

[**WHEA_XPF_CMC_DESCRIPTOR**](./ns-ntddk-_whea_xpf_cmc_descriptor.md)