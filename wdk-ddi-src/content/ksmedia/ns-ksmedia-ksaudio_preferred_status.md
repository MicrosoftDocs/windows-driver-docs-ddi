---
UID: NS:ksmedia.KSAUDIO_PREFERRED_STATUS
title: KSAUDIO_PREFERRED_STATUS
author: windows-driver-content
description: The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.
old-location: audio\ksaudio_preferred_status.htm
old-project: audio
ms.assetid: 3191aeff-7324-4c2b-9b64-ddc50a561df5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSAUDIO_PREFERRED_STATUS, KSAUDIO_PREFERRED_STATUS, KSAUDIO_PREFERRED_STATUS structure [Audio Devices], PKSAUDIO_PREFERRED_STATUS, PKSAUDIO_PREFERRED_STATUS structure pointer [Audio Devices], aud-prop_a1287dc0-98ad-4071-be11-41e51b6b4846.xml, audio.ksaudio_preferred_status, ksmedia/KSAUDIO_PREFERRED_STATUS, ksmedia/PKSAUDIO_PREFERRED_STATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSAUDIO_PREFERRED_STATUS
product: Windows
targetos: Windows
req.typenames: KSAUDIO_PREFERRED_STATUS, *PKSAUDIO_PREFERRED_STATUS
---

# KSAUDIO_PREFERRED_STATUS structure


## -description


The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.


## -syntax


````
typedef struct {
  BOOL                             Enable;
  KSPROPERTY_SYSAUDIO_DEFAULT_TYPE DeviceType;
  ULONG                            Flags;
  ULONG                            Reserved;
} KSAUDIO_PREFERRED_STATUS, *PKSAUDIO_PREFERRED_STATUS;
````


## -struct-fields




### -field Enable

Specifies whether the target device is the new preferred device. If <b>TRUE</b>, the target device is selected as the new preferred device. If <b>FALSE</b>, the target device was previously the preferred device, but is now deselected.


### -field DeviceType

Specifies the type of preferred device. This parameter is set to one of the following constants:

<table>
<tr>
<th>Value</th>
<th>Device type</th>
</tr>
<tr>
<td>
KSPROPERTY_SYSAUDIO_NORMAL_DEFAULT

</td>
<td>
Preferred device for wave playback/recording, MIDI, and mixer topology.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SYSAUDIO_PLAYBACK_DEFAULT

</td>
<td>
Preferred wave playback device.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SYSAUDIO_RECORD_DEFAULT

</td>
<td>
Preferred wave recording device.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SYSAUDIO_MIDI_DEFAULT

</td>
<td>
Preferred MIDI device.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SYSAUDIO_MIXER_DEFAULT

</td>
<td>
Preferred mixer topology device.

</td>
</tr>
</table>
 

The driver uses this member to determine what aspect or aspects of the audio adapter are currently selected as preferred. A driver might use this information to decide how to configure itself or decide what system resources to request.


### -field Flags

No flags are currently defined. Set to zero.


### -field Reserved

Reserved for future use. Set to zero.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537299">KSPROPERTY_AUDIO_PREFERRED_STATUS</a> property.

For information about the preferred device, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537899">SetupPreferredAudioDevices</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537299">KSPROPERTY_AUDIO_PREFERRED_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537899">SetupPreferredAudioDevices</a>



 

 


