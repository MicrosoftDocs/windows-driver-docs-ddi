---
UID: NS:ksmedia.KSAUDIO_PREFERRED_STATUS
title: KSAUDIO_PREFERRED_STATUS (ksmedia.h)
description: The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.
tech.root: audio
ms.date: 03/10/2023
keywords: ["KSAUDIO_PREFERRED_STATUS structure"]
ms.keywords: "*PKSAUDIO_PREFERRED_STATUS, KSAUDIO_PREFERRED_STATUS, KSAUDIO_PREFERRED_STATUS structure [Audio Devices], PKSAUDIO_PREFERRED_STATUS, PKSAUDIO_PREFERRED_STATUS structure pointer [Audio Devices], aud-prop_a1287dc0-98ad-4071-be11-41e51b6b4846.xml, audio.ksaudio_preferred_status, ksmedia/KSAUDIO_PREFERRED_STATUS, ksmedia/PKSAUDIO_PREFERRED_STATUS"
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
req.typenames: KSAUDIO_PREFERRED_STATUS, *PKSAUDIO_PREFERRED_STATUS
f1_keywords:
 - PKSAUDIO_PREFERRED_STATUS
 - ksmedia/PKSAUDIO_PREFERRED_STATUS
 - KSAUDIO_PREFERRED_STATUS
 - ksmedia/KSAUDIO_PREFERRED_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSAUDIO_PREFERRED_STATUS
 - KSAUDIO_PREFERRED_STATUS
---

## -description

The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.

## -struct-fields

### -field Enable

Specifies whether the target device is the new preferred device. If **TRUE**, the target device is selected as the new preferred device. If **FALSE**, the target device was previously the preferred device, but is now deselected.

### -field DeviceType

Specifies the type of preferred device. This parameter is set to one of the following constants:

| Value | Device type |
|---|---|
| KSPROPERTY_SYSAUDIO_NORMAL_DEFAULT | Preferred device for wave playback/recording, MIDI, and mixer topology. |
| KSPROPERTY_SYSAUDIO_PLAYBACK_DEFAULT | Preferred wave playback device. |
| KSPROPERTY_SYSAUDIO_RECORD_DEFAULT | Preferred wave recording device. |
| KSPROPERTY_SYSAUDIO_MIDI_DEFAULT | Preferred MIDI device. |
| KSPROPERTY_SYSAUDIO_MIXER_DEFAULT | Preferred mixer topology device. |

The driver uses this member to determine what aspect or aspects of the audio adapter are currently selected as preferred. A driver might use this information to decide how to configure itself or decide what system resources to request.

### -field Flags

No flags are currently defined. Set to zero.

### -field Reserved

Reserved for future use. Set to zero.

## -remarks

This structure is used by the [KSPROPERTY_AUDIO_PREFERRED_STATUS](/windows-hardware/drivers/audio/ksproperty-audio-preferred-status) property.

For information about the preferred device, see [SetupPreferredAudioDevices](/windows-hardware/drivers/audio/setuppreferredaudiodevices).

## -see-also

[KSPROPERTY_AUDIO_PREFERRED_STATUS](/windows-hardware/drivers/audio/ksproperty-audio-preferred-status)

[SetupPreferredAudioDevices](/windows-hardware/drivers/audio/setuppreferredaudiodevices)
