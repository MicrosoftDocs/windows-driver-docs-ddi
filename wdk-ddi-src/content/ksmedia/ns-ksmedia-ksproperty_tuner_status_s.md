---
UID: NS:ksmedia.__unnamed_struct_104
title: KSPROPERTY_TUNER_STATUS_S (ksmedia.h)
description: The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.
old-location: stream\ksproperty_tuner_status_s.htm
tech.root: stream
ms.date: 04/30/2019
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
 - KSPROPERTY_TUNER_STATUS_S
---

# KSPROPERTY_TUNER_STATUS_S structure


## -description

The KSPROPERTY_TUNER_STATUS_S structure describes the progress of a tuning operation for TV and radio tuner devices, including present tuning frequency.

## -struct-fields

### -field Property

Specifies an initialized <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

### -field CurrentFrequency

Specifies the current tuner frequency. This value is in hertz (Hz).

### -field PLLOffset

Specifies the phase locked loop (PLL) offset in multiples of the tuning granularity. This is used if the tuner strategy is KS_TUNER_STRATEGY_PLL. If the tuner strategy is not KS_TUNER_STRATEGY_PLL, this value has no meaning. The following table demonstrates the value to be returned by the minidriver for various tuning conditions, assuming the tuning granularity is 62.5kHz:

<table>
<tr>
<th>Frequency Offset</th>
<th>PLLOffset</th>
</tr>
<tr>
<td>
+125,000

</td>
<td>
+2

</td>
</tr>
<tr>
<td>
+62,500

</td>
<td>
+1

</td>
</tr>
<tr>
<td>
Perfectly tuned

</td>
<td>
0

</td>
</tr>
<tr>
<td>
-62,500

</td>
<td>
-1

</td>
</tr>
<tr>
<td>
-125,000

</td>
<td>
-2

</td>
</tr>
</table>

### -field SignalStrength

Specifies the amplitude of the signal. This is used if the tuner strategy is KS_TUNER_STRATEGY_SIGNAL_STRENGTH. Regardless of the tuning strategy supported by the minidriver, the valid values for this member are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
-1

</td>
<td>
Strength not Available.

</td>
</tr>
<tr>
<td>
0

</td>
<td>
Not on an acceptable frequency.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
On an acceptable frequency.

</td>
</tr>
</table>

### -field Busy

Indicates if the minidriver is presently busy with the process of tuning. This member must be set to <b>TRUE</b> if the minidriver is currently tuning to a channel. Otherwise, if the minidriver is not currently tuning to a new channel, this member must be set to <b>FALSE</b>.

## -remarks

For more information about the <b>PLLOffset</b> and <b>SignalStrength</b> members see <a href="/windows-hardware/drivers/stream/pci-based-tv-capture">PCI based TV capture</a>. If your tuner device supports radio tuning, see <a href="/windows-hardware/drivers/stream/video-capture-devices-with-radio-tuners">Video Capture Devices with Radio Tuners</a>.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-tuner-status">KSPROPERTY_TUNER_STATUS</a>



<a href="/windows-hardware/drivers/stream/propsetid-tuner">PROPSETID_TUNER</a>
