---
UID: NS:ksmedia.KSDS3D_ITD_PARAMS
title: KSDS3D_ITD_PARAMS
author: windows-driver-content
description: The KSDS3D_ITD_PARAMS structure specifies the parameters applied by the interaural time delay (ITD) algorithm to the left or right channel in a 3D node (KSNODETYPE_3D_EFFECTS).
old-location: audio\ksds3d_itd_params.htm
old-project: audio
ms.assetid: 2c8701d5-c762-4d2c-abd7-8da90292f3c0
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSDS3D_ITD_PARAMS, KSDS3D_ITD_PARAMS, KSDS3D_ITD_PARAMS structure [Audio Devices], PKSDS3D_ITD_PARAMS, PKSDS3D_ITD_PARAMS structure pointer [Audio Devices], aud-prop_169748c9-f538-47d2-ae3c-ae34cca26f00.xml, audio.ksds3d_itd_params, ksmedia/KSDS3D_ITD_PARAMS, ksmedia/PKSDS3D_ITD_PARAMS"
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
-	KSDS3D_ITD_PARAMS
product: Windows
targetos: Windows
req.typenames: KSDS3D_ITD_PARAMS, *PKSDS3D_ITD_PARAMS
---

# KSDS3D_ITD_PARAMS structure


## -description


The KSDS3D_ITD_PARAMS structure specifies the parameters applied by the interaural time delay (ITD) algorithm to the left or right channel in a 3D node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>).


## -struct-fields




### -field Channel

Specifies the channel number (channel 0 is the left channel; channel 1 is the right channel).


### -field VolSmoothScale

Specifies the ramp factor for scaling volume levels. For more information, see the following Remarks section.


### -field TotalDryAttenuation

Specifies the attenuation factor for the "dry" signal (the original signal before applying a low-pass filter to produce a muffled effect). For more information, see the following Remarks section.


### -field TotalWetAttenuation

Specifies the attenuation factor for the "wet" signal (the muffled signal after the low-pass filter is applied). For more information, see the following Remarks section.


### -field SmoothFrequency

Specifies the sample frequency of the audio stream. When changing to a new <b>TotalDryAttenuation</b> or <b>TotalWetAttenuation</b> value, the ITD algorithm needs this value to determine the number of samples over which to apply smoothing in order to complete the transition within some fixed time interval. For example, the ITD algorithm implemented by the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">KMixer system driver</a> uses a transition time interval of roughly 1/8 second.


### -field Delay

Specifies the time delay for this channel. The delay is expressed as an integer number of samples.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537114">KSDS3D_ITD_PARAMS_MSG</a> structure, which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537358">KSPROPERTY_ITD3D_PARAMS</a> property request uses to specify the ITD parameters for the left and right channels of a 3D audio stream.

The <b>Delay</b> member specifies the amount by which the current channel delays the sound arriving from the source. The interaural time delay is the difference in delays between the two channels.

The attenuated signal is the sum of the attenuated dry signal and the attenuated wet signal:

<b>TotalDryAttenuation</b>*
    <i>&lt;dry sample&gt;</i>
    +<b>TotalWetAttenuation</b>*
    <i>&lt;wet sample&gt;</i>

Increasing the size of <b>TotalWetAttenuation</b> relative to <b>TotalDryAttenuation</b> produces an increasingly muffled sound. The two attenuation factors are calculated from the sound source's position, orientation, and sound cone.

When a KSPROPERTY_ITD3D_PARAMS set-property request changes either <b>TotalDryAttenuation</b> or <b>TotalWetAttenuation</b>, the change in attenuation level is smoothed over a number of samples in order to avoid generating spurious clicking noises. The <b>VolSmoothScale</b> member specifies the amount by which to scale the attenuation of the signal during each step in the smoothing process. This parameter is either a value slightly less than 1 if the attenuation is increasing or slightly greater than 1 if the attenuation is decreasing. At each step in the smoothing process, the attenuation from the previous step is multiplied by this parameter. The process completes when the target attenuation is reached.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537114">KSDS3D_ITD_PARAMS_MSG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537358">KSPROPERTY_ITD3D_PARAMS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_ITD_PARAMS structure%20 RELEASE:%20(3/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

