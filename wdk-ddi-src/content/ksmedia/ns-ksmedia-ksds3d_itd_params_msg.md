---
UID: NS:ksmedia.__unnamed_struct_19
title: KSDS3D_ITD_PARAMS_MSG (ksmedia.h)
description: The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (KSNODETYPE_3D_EFFECTS).
old-location: audio\ksds3d_itd_params_msg.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["KSDS3D_ITD_PARAMS_MSG structure"]
ms.keywords: "*PKSDS3D_ITD_PARAMS_MSG, KSDS3D_ITD_PARAMS_MSG, KSDS3D_ITD_PARAMS_MSG structure [Audio Devices], PKSDS3D_ITD_PARAMS_MSG, PKSDS3D_ITD_PARAMS_MSG structure pointer [Audio Devices], aud-prop_af31be2f-c153-4430-9634-6d29b05208dd.xml, audio.ksds3d_itd_params_msg, ksmedia/KSDS3D_ITD_PARAMS_MSG, ksmedia/PKSDS3D_ITD_PARAMS_MSG"
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
req.typenames: KSDS3D_ITD_PARAMS_MSG, *PKSDS3D_ITD_PARAMS_MSG
f1_keywords:
 - PKSDS3D_ITD_PARAMS_MSG
 - ksmedia/PKSDS3D_ITD_PARAMS_MSG
 - KSDS3D_ITD_PARAMS_MSG
 - ksmedia/KSDS3D_ITD_PARAMS_MSG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSDS3D_ITD_PARAMS_MSG
 - KSDS3D_ITD_PARAMS_MSG
---

# KSDS3D_ITD_PARAMS_MSG structure


## -description

The KSDS3D_ITD_PARAMS_MSG structure specifies the parameters used by the interaural time delay (ITD) algorithm in a 3D node (<a href="/windows-hardware/drivers/audio/ksnodetype-3d-effects">KSNODETYPE_3D_EFFECTS</a>).

## -struct-fields

### -field Enabled

Specifies whether to enable the ITD algorithm. A nonzero value enables the algorithm. Zero disables it. For more information, see the following Remarks section.

### -field LeftParams

Specifies the ITD parameters for the left channel (channel 0). This parameter is a structure of type <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_itd_params">KSDS3D_ITD_PARAMS</a>.

### -field RightParams

Specifies the ITD parameters for the right channel (channel 1). This parameter is a structure of type KSDS3D_ITD_PARAMS.

### -field Reserved

Reserved. Set to zero.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/audio/ksproperty-itd3d-params">KSPROPERTY_ITD3D_PARAMS</a> property request.

The <i>Enabled</i> parameter should track the DirectSound buffer's 3D mode: Disable ITD processing when the 3D mode is disabled, and enable it when the 3D mode is enabled. For more information, see the description of the <b>DirectSound3DBuffer::SetMode</b> method in the Microsoft Windows SDK documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_itd_params">KSDS3D_ITD_PARAMS</a>



<a href="/windows-hardware/drivers/audio/ksnodetype-3d-effects">KSNODETYPE_3D_EFFECTS</a>



<a href="/windows-hardware/drivers/audio/ksproperty-itd3d-params">KSPROPERTY_ITD3D_PARAMS</a>

