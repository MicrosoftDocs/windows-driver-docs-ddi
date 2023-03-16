---
UID: NS:ksmedia.KSPROPERTY_TUNER_STATUS_S
title: KSPROPERTY_TUNER_STATUS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.
tech.root: stream
ms.date: 03/14/2023
keywords: ["KSPROPERTY_TUNER_STATUS_S structure"]
ms.keywords: "*PKSPROPERTY_TUNER_STATUS_S, KSPROPERTY_TUNER_STATUS_S, KSPROPERTY_TUNER_STATUS_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STATUS_S, PKSPROPERTY_TUNER_STATUS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_STATUS_S, ksmedia/PKSPROPERTY_TUNER_STATUS_S, stream.ksproperty_tuner_status_s, vidcapstruct_a36247d8-99d7-4dad-8632-5feb685616d6.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
req.typenames: KSPROPERTY_TUNER_STATUS_S, *PKSPROPERTY_TUNER_STATUS_S
f1_keywords:
 - PKSPROPERTY_TUNER_STATUS_S
 - ksmedia/PKSPROPERTY_TUNER_STATUS_S
 - KSPROPERTY_TUNER_STATUS_S
 - ksmedia/KSPROPERTY_TUNER_STATUS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSPROPERTY_TUNER_STATUS_S
 - KSPROPERTY_TUNER_STATUS_S
---

## -description

The **KSPROPERTY_TUNER_STATUS_S** structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.

## -struct-fields

### -field Property

Specifies an initialized [KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure) structure that describes the property set, property ID, and request type.

### -field CurrentFrequency

Specifies the current tuner frequency. This value is in hertz (Hz).

### -field PLLOffset

Specifies the phase locked loop (PLL) offset in multiples of the tuning granularity. This is used if the tuner strategy is KS_TUNER_STRATEGY_PLL. If the tuner strategy is not KS_TUNER_STRATEGY_PLL, this value has no meaning. The following table demonstrates the value to be returned by the minidriver for various tuning conditions, assuming the tuning granularity is 62.5kHz:

| Frequency Offset | PLLOffset |
|---|---|
| +125,000 | +2 |
| +62,500 | +1 |
| Perfectly tuned | 0 |
| -62,500 | -1 |
| -125,000 | -2 |

### -field SignalStrength

Specifies the amplitude of the signal. This is used if the tuner strategy is KS_TUNER_STRATEGY_SIGNAL_STRENGTH. Regardless of the tuning strategy supported by the minidriver, the valid values for this member are:

| Value | Meaning |
|---|---|
| -1 | Strength not Available. |
| 0 | Not on an acceptable frequency. |
| 1 | On an acceptable frequency. |

### -field Busy

Indicates if the minidriver is presently busy with the process of tuning. This member must be set to **TRUE** if the minidriver is currently tuning to a channel. Otherwise, if the minidriver is not currently tuning to a new channel, this member must be set to **FALSE**.

## -remarks

For more information about the **PLLOffset** and **SignalStrength** members see [PCI based TV capture](/windows-hardware/drivers/stream/pci-based-tv-capture). If your tuner device supports radio tuning, see [Video Capture Devices with Radio Tuners](/windows-hardware/drivers/stream/video-capture-devices-with-radio-tuners).

## -see-also

[KSPROPERTY](/windows-hardware/drivers/stream/ksproperty-structure)

[KSPROPERTY_TUNER_STATUS](/windows-hardware/drivers/stream/ksproperty-tuner-status)

[PROPSETID_TUNER](/windows-hardware/drivers/stream/propsetid-tuner)
