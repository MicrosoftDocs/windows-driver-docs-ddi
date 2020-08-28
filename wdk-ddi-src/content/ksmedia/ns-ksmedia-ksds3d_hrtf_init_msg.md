---
UID: NS:ksmedia.__unnamed_struct_16
title: KSDS3D_HRTF_INIT_MSG (ksmedia.h)
description: The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_init_msg.htm
tech.root: audio
ms.assetid: 8e25a1e2-24b1-418c-b1eb-884bdbad63b3
ms.date: 05/08/2018
keywords: ["KSDS3D_HRTF_INIT_MSG structure"]
ms.keywords: "*PKSDS3D_HRTF_INIT_MSG, KSDS3D_HRTF_INIT_MSG, KSDS3D_HRTF_INIT_MSG structure [Audio Devices], PKSDS3D_HRTF_INIT_MSG, PKSDS3D_HRTF_INIT_MSG structure pointer [Audio Devices], aud-prop_f9994a16-7d3c-43af-b423-c6afc64c05b9.xml, audio.ksds3d_hrtf_init_msg, ksmedia/KSDS3D_HRTF_INIT_MSG, ksmedia/PKSDS3D_HRTF_INIT_MSG"
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
req.typenames: KSDS3D_HRTF_INIT_MSG, *PKSDS3D_HRTF_INIT_MSG
f1_keywords:
 - PKSDS3D_HRTF_INIT_MSG
 - ksmedia/PKSDS3D_HRTF_INIT_MSG
 - KSDS3D_HRTF_INIT_MSG
 - ksmedia/KSDS3D_HRTF_INIT_MSG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSDS3D_HRTF_INIT_MSG
---

# KSDS3D_HRTF_INIT_MSG structure


## -description

The KSDS3D_HRTF_INIT_MSG structure specifies the parameter settings to use to initialize the head-relative transfer function (HRTF).

## -struct-fields

### -field Size

Specifies the size in bytes of the structure.

### -field Quality

Specifies the HRTF filter quality level. Set this parameter to one of the following KSDS3D_HRTF_FILTER_QUALITY enumeration values:

<ul>
<li>
LIGHT_FILTER selects an efficient algorithm that produces a good quality effect.

</li>
<li>
FULL_FILTER selects an algorithm that produces a high-quality effect but requires more processing time.

</li>
</ul>

### -field SampleRate

Specifies the sample rate, in samples per second (hertz), at which each channel should be played. For example, a value of 22,050 specifies a sample rate of 22.05 kHz.

### -field MaxFilterSize

Specifies the maximum filter size in bytes. If the filter is in direct form, the maximum size is the order of the filter (numerator and denominator have equal order). If the filter is in cascade form, the maximum size is the maximum number of biquadratic coefficients.

### -field FilterTransientMuteLength

Specifies how long to delay cross-fading to the new filter in order to avoid introducing the new filter's initial transient signal into the output signal. The delay is specified as a number of initial samples produced by the new filter. During this time, the output comes from the old filters only.

### -field FilterOverlapBufferLength

Specifies the total number of samples over which to mute and cross-fade the filter outputs.

### -field OutputOverlapBufferLength

Specifies the number of samples over which to cross-fade the output channels after a transition across azimuth angle zero. This member is used when cross-fading of the output channels is enabled by the <b>CrossFadeOutput</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_hrtf_params_msg">KSDS3D_HRTF_PARAMS_MSG</a>.

### -field Reserved

Reserved. Set to zero.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-hrtf3d-initialize">KSPROPERTY_HRTF3D_INITIALIZE</a> property.

The <b>Quality</b> values FULL_FILTER and LIGHT_FILTER correspond to the GUID_DS3DALG_HRTF_FULL and GUID_DS3DALG_HRTF_LIGHT settings that are described in the Microsoft Windows SDK documentation.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-hrtf3d">KSPROPSETID_Hrtf3d</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_hrtf_params_msg">KSDS3D_HRTF_PARAMS_MSG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-hrtf3d-initialize">KSPROPERTY_HRTF3D_INITIALIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-hrtf3d">KSPROPSETID_Hrtf3d</a>

