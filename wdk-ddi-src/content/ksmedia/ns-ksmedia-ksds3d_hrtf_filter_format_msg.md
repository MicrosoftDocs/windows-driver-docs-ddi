---
UID: NS:ksmedia.__unnamed_struct_17
title: KSDS3D_HRTF_FILTER_FORMAT_MSG
description: The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_filter_format_msg.htm
tech.root: audio
ms.assetid: c0122c96-5bd3-4c1f-85d3-5d4ead5c0c86
ms.date: 05/08/2018
ms.keywords: "*PKSDS3D_HRTF_FILTER_FORMAT_MSG, KSDS3D_HRTF_FILTER_FORMAT_MSG, KSDS3D_HRTF_FILTER_FORMAT_MSG structure [Audio Devices], PKSDS3D_HRTF_FILTER_FORMAT_MSG, PKSDS3D_HRTF_FILTER_FORMAT_MSG structure pointer [Audio Devices], aud-prop_5ad5b67d-5302-44e1-b4e0-16d66334f57b.xml, audio.ksds3d_hrtf_filter_format_msg, ksmedia/KSDS3D_HRTF_FILTER_FORMAT_MSG, ksmedia/PKSDS3D_HRTF_FILTER_FORMAT_MSG"
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
-	KSDS3D_HRTF_FILTER_FORMAT_MSG
product:
- Windows
targetos: Windows
req.typenames: KSDS3D_HRTF_FILTER_FORMAT_MSG, *PKSDS3D_HRTF_FILTER_FORMAT_MSG
---

# KSDS3D_HRTF_FILTER_FORMAT_MSG structure


## -description


The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF).


## -struct-fields




### -field FilterMethod

Specifies the filter method to use. Set this parameter to one of the following KSDS3D_HRTF_FILTER_METHOD enumeration values:

<ul>
<li>
DIRECT_FORM

</li>
<li>
CASCADE_FORM

</li>
</ul>
For more information, see the description of the <b>MaxFilterSize</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537106">KSDS3D_HRTF_INIT_MSG</a>.


### -field CoeffFormat

Specifies the coefficient format to use. Set this parameter to one of the following KSDS3D_HRTF_COEFF_FORMAT enumeration values:

<ul>
<li>
FLOAT_COEFF specifies floating-point coefficients.

</li>
<li>
SHORT_COEFF specifies 16-bit integer coefficients.

</li>
</ul>

### -field Version

Specifies the filter version. Set this parameter to the KSDS3D_HRTF_FILTER_VERSION enumeration value DS3D_HRTF_VERSION_1.


### -field Reserved

Reserved. Set to zero.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537353">KSPROPERTY_HRTF3D_FILTER_FORMAT</a> property.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537353">KSPROPERTY_HRTF3D_FILTER_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>
 

 

