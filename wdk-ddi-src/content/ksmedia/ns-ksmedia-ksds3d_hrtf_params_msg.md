---
UID: NS:ksmedia.__unnamed_struct_15
title: KSDS3D_HRTF_PARAMS_MSG (ksmedia.h)
description: The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_params_msg.htm
tech.root: audio
ms.assetid: e746fc3d-ebfd-41a1-b640-6f803423bd95
ms.date: 05/08/2018
ms.keywords: "*PKSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG structure [Audio Devices], PKSDS3D_HRTF_PARAMS_MSG, PKSDS3D_HRTF_PARAMS_MSG structure pointer [Audio Devices], aud-prop_1f9e726f-d9b6-43e5-8c6e-82e645587ca4.xml, audio.ksds3d_hrtf_params_msg, ksmedia/KSDS3D_HRTF_PARAMS_MSG, ksmedia/PKSDS3D_HRTF_PARAMS_MSG"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSDS3D_HRTF_PARAMS_MSG
product:
- Windows
targetos: Windows
req.typenames: KSDS3D_HRTF_PARAMS_MSG, *PKSDS3D_HRTF_PARAMS_MSG
---

# KSDS3D_HRTF_PARAMS_MSG structure


## -description


The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).


## -struct-fields




### -field Size

Specifies the size in bytes of the structure.


### -field Enabled

Specifies whether to enable HRTF processing. If nonzero, HRTF is enabled. If zero, it is disabled.


### -field SwapChannels

Specifies whether the algorithm should swap channels. If <b>TRUE</b>, the algorithm should swap the channels to perform a left-to-right reversal of the location of the source. If <b>FALSE</b>, the algorithm should not swap the channels.


### -field ZeroAzimuth

Specifies whether the azimuth angle is zero. If <b>TRUE</b>, then only half of the filter coefficients are downloaded to the filter because the azimuth angle is zero. If <b>FALSE</b>, all the coefficients are downloaded.


### -field CrossFadeOutput

Specifies whether to cross-fade the output channels after crossing azimuth angle zero. If <b>TRUE</b>, the algorithm should cross-fade the output channels. If <b>FALSE</b>, it should not cross-fade the channels.


### -field FilterSize

Specifies the additional size in bytes of the filter coefficients that are appended to this structure.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a> property.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>
 

 

