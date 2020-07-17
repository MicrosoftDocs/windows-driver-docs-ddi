---
UID: NS:ksmedia.__unnamed_struct_105
title: TUNER_ANALOG_CAPS_S (ksmedia.h)
description: The TUNER_ANALOG_CAPS_S structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network.
old-location: stream\tuner_analog_caps_s.htm
tech.root: stream
ms.assetid: 350ec4b2-a96a-420a-bb52-d09cc8c5029e
ms.date: 04/30/2019
keywords: ["TUNER_ANALOG_CAPS_S structure"]
ms.keywords: "*PTUNER_ANALOG_CAPS_S, PTUNER_ANALOG_CAPS_S, PTUNER_ANALOG_CAPS_S structure pointer [Streaming Media Devices], TUNER_ANALOG_CAPS_S, TUNER_ANALOG_CAPS_S structure [Streaming Media Devices], ksmedia/PTUNER_ANALOG_CAPS_S, ksmedia/TUNER_ANALOG_CAPS_S, stream.tuner_analog_caps_s, vidcapstruct_47de7e8b-b88a-4ae7-87eb-ed9fa008eccb.xml"
f1_keywords:
 - "ksmedia/TUNER_ANALOG_CAPS_S"
 - "TUNER_ANALOG_CAPS_S"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- TUNER_ANALOG_CAPS_S
product:
- Windows
targetos: Windows
req.typenames: TUNER_ANALOG_CAPS_S, *PTUNER_ANALOG_CAPS_S
---

# TUNER_ANALOG_CAPS_S structure


## -description


The TUNER_ANALOG_CAPS_S structure describes the hardware scanning capabilities of a tuning device that supports an analog broadcast network.


## -struct-fields




### -field Mode

The current tuner mode, which can be represented by one of the following tuner mode flags from the KSPROPERTY_TUNER_MODES enumeration that is defined in <i>Ksmedia.h.</i>

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_TV

</td>
<td>
The tuner is currently tuning broadcast or cable television channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_FM_RADIO

</td>
<td>
The tuner is currently tuning FM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_AM_RADIO

</td>
<td>
The tuner is currently tuning AM radio channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_DSS

</td>
<td>
The tuner is currently tuning DSS channels.

</td>
</tr>
<tr>
<td>
KSPROPERTY_TUNER_MODE_ATSC

</td>
<td>
The tuner is capable of tuning Advanced Television Systems Committee broadcasts (Digital TV for the United States). This setting can also be used by DVB-T and DVB-C systems.

</td>
</tr>
</table>
 


### -field StandardsSupported

If the <b>Mode</b> member is set to KSPROPERTY_TUNER_MODE_TV or KSPROPERTY_TUNER_MODE_DSS, a bitwise OR of values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a> enumeration that indicates the analog video standards that the tuner supports. Otherwise, this member is ignored.


### -field MinFrequency

The lowest frequency, in Hz, that the tuner supports. 


### -field MaxFrequency

The highest frequency, in Hz, that the tuner supports. 


### -field TuningGranularity

The smallest possible step size, in Hz, between two settings of the tuning frequency. 


### -field SettlingTime

The time, in milliseconds, for a new frequency setting to become stable.

<i>KsTvTune.ax</i> uses the value in <b>SettlingTime</b> to evaluate the total time its scanning algorithm might take so that it can determine wait time. The value in <b>SettlingTime</b> along with the number of stepping increments in the entire frequency range that is based on the sensing range should provide an estimate of the total time that is required for the scanning algorithm. 


### -field ScanSensingRange

The range that the tuning device provides and that the tuner filter uses to determine the presence of a signal. This range represents the larger step sizes that a signal search algorithm can use to advance through the range of frequencies to search. The driver can report the actual lock frequency of a signal and the lock status on the signal through a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-status">KSPROPERTY_TUNER_SCAN_STATUS</a> property. If the driver reports the lock status as Tuner_LockType_Within_Scan_Sensing_Range in the <b>LockStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_status_s">KSPROPERTY_TUNER_SCAN_STATUS_S</a> structure, the increment step size changes to the smaller value in <b>FineTuneSensingRange</b> until the actual lock frequency is determined. 


### -field FineTuneSensingRange

The range that the tuning device provides and that the tuner filter uses to determine the actual frequency of a signal. The tuner filter uses this fine-tune-sensing range only when the underlying tuner hardware cannot support hardware-assisted scanning. The driver indicates such support by setting the <b>fSupportsHardwareAssistedScanning</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s">KSPROPERTY_TUNER_SCAN_CAPS_S</a> structure to <b>TRUE</b> in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a> property. When the tuner filter starts a scan, it initially probes the driver in increments within the range that the <b>ScanSensingRange</b> member specifies until the driver returns Tuner_LockType_Within_Scan_Sensing_Range. The tuner filter then switches into steps of <b>FineTuneSensingRange</b> until the driver reports a complete lock. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-caps">KSPROPERTY_TUNER_SCAN_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_caps_s">KSPROPERTY_TUNER_SCAN_CAPS_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-tuner-scan-status">KSPROPERTY_TUNER_SCAN_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_tuner_scan_status_s">KSPROPERTY_TUNER_SCAN_STATUS_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-ks_analogvideostandard">KS_AnalogVideoStandard</a>
 

 

