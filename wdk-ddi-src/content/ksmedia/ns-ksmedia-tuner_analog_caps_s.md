---
UID: NS:ksmedia.TUNER_ANALOG_CAPS_S
title: TUNER_ANALOG_CAPS_S (ksmedia.h)
description: The TUNER_ANALOG_CAPS_S structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network.
tech.root: stream
ms.date: 03/15/2023
keywords: ["TUNER_ANALOG_CAPS_S structure"]
ms.keywords: "*PTUNER_ANALOG_CAPS_S, PTUNER_ANALOG_CAPS_S, PTUNER_ANALOG_CAPS_S structure pointer [Streaming Media Devices], TUNER_ANALOG_CAPS_S, TUNER_ANALOG_CAPS_S structure [Streaming Media Devices], ksmedia/PTUNER_ANALOG_CAPS_S, ksmedia/TUNER_ANALOG_CAPS_S, stream.tuner_analog_caps_s, vidcapstruct_47de7e8b-b88a-4ae7-87eb-ed9fa008eccb.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
req.typenames: TUNER_ANALOG_CAPS_S, *PTUNER_ANALOG_CAPS_S
f1_keywords:
 - PTUNER_ANALOG_CAPS_S
 - ksmedia/PTUNER_ANALOG_CAPS_S
 - TUNER_ANALOG_CAPS_S
 - ksmedia/TUNER_ANALOG_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PTUNER_ANALOG_CAPS_S
 - TUNER_ANALOG_CAPS_S
---

## -description

The **TUNER_ANALOG_CAPS_S** structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network.

## -struct-fields

### -field Mode

The current tuner mode, which can be represented by one of the following tuner mode flags from the KSPROPERTY_TUNER_MODES enumeration that is defined in *Ksmedia.h.*

| Flag | Meaning |
|---|---|
| KSPROPERTY_TUNER_MODE_TV | The tuner is currently tuning broadcast or cable television channels. |
| KSPROPERTY_TUNER_MODE_FM_RADIO | The tuner is currently tuning FM radio channels. |
| KSPROPERTY_TUNER_MODE_AM_RADIO | The tuner is currently tuning AM radio channels. |
| KSPROPERTY_TUNER_MODE_DSS | The tuner is currently tuning DSS channels. |
| KSPROPERTY_TUNER_MODE_ATSC | The tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems. |

### -field StandardsSupported

If the **Mode** member is set to KSPROPERTY_TUNER_MODE_TV or KSPROPERTY_TUNER_MODE_DSS, a bitwise OR of values from the [KS_AnalogVideoStandard](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard) enumeration that indicates the analog video standards that the tuner supports. Otherwise, this member is ignored.

### -field MinFrequency

The lowest frequency, in Hz, that the tuner supports.

### -field MaxFrequency

The highest frequency, in Hz, that the tuner supports.

### -field TuningGranularity

The smallest possible step size, in Hz, between two settings of the tuning frequency.

### -field SettlingTime

The time, in milliseconds, for a new frequency setting to become stable.

*KsTvTune.ax* uses the value in **SettlingTime** to evaluate the total time its scanning algorithm might take so that it can determine wait time. The value in **SettlingTime** along with the number of stepping increments in the entire frequency range that is based on the sensing range should provide an estimate of the total time that is required for the scanning algorithm.

### -field ScanSensingRange

The range that the tuning device provides and that the tuner filter uses to determine the presence of a signal. This range represents the larger step sizes that a signal search algorithm can use to advance through the range of frequencies to search. The driver can report the actual lock frequency of a signal and the lock status on the signal through a call to the driver's [KSPROPERTY_TUNER_SCAN_STATUS](/windows-hardware/drivers/stream/ksproperty-tuner-scan-status) property. If the driver reports the lock status as Tuner_LockType_Within_Scan_Sensing_Range in the **LockStatus** member of the [**KSPROPERTY_TUNER_SCAN_STATUS_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_status_s) structure, the increment step size changes to the smaller value in **FineTuneSensingRange** until the actual lock frequency is determined.

### -field FineTuneSensingRange

The range that the tuning device provides and that the tuner filter uses to determine the actual frequency of a signal. The tuner filter uses this fine-tune-sensing range only when the underlying tuner hardware cannot support hardware-assisted scanning. The driver indicates such support by setting the **fSupportsHardwareAssistedScanning** member of the [**KSPROPERTY_TUNER_SCAN_CAPS_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s) structure to **TRUE** in a call to its [KSPROPERTY_TUNER_SCAN_CAPS](/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps) property. When the tuner filter starts a scan, it initially probes the driver in increments within the range that the **ScanSensingRange** member specifies until the driver returns Tuner_LockType_Within_Scan_Sensing_Range. The tuner filter then switches into steps of **FineTuneSensingRange** until the driver reports a complete lock.

## -see-also

[KSPROPERTY_TUNER_SCAN_CAPS](/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps)

[**KSPROPERTY_TUNER_SCAN_CAPS_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s)

[KSPROPERTY_TUNER_SCAN_STATUS](/windows-hardware/drivers/stream/ksproperty-tuner-scan-status)

[**KSPROPERTY_TUNER_SCAN_STATUS_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_status_s)

[**KS_AnalogVideoStandard**](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard)
