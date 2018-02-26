---
UID: NS:ksmedia.KSDS3D_HRTF_FILTER_FORMAT_MSG
title: KSDS3D_HRTF_FILTER_FORMAT_MSG
author: windows-driver-content
description: The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_filter_format_msg.htm
old-project: audio
ms.assetid: c0122c96-5bd3-4c1f-85d3-5d4ead5c0c86
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSDS3D_HRTF_FILTER_FORMAT_MSG, ,, 3, A, D, E, F, G, H, I, K, KSDS3D_HRTF_FILTER_FORMAT_MSG, KSDS3D_HRTF_FILTER_FORMAT_MSG structure [Audio Devices], L, M, O, P, PKSDS3D_HRTF_FILTER_FORMAT_MSG, PKSDS3D_HRTF_FILTER_FORMAT_MSG structure pointer [Audio Devices], R, S, T, _, aud-prop_5ad5b67d-5302-44e1-b4e0-16d66334f57b.xml, audio.ksds3d_hrtf_filter_format_msg, ksmedia/KSDS3D_HRTF_FILTER_FORMAT_MSG, ksmedia/PKSDS3D_HRTF_FILTER_FORMAT_MSG"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSDS3D_HRTF_FILTER_FORMAT_MSG
product: Windows
targetos: Windows
req.typenames: KSDS3D_HRTF_FILTER_FORMAT_MSG, *PKSDS3D_HRTF_FILTER_FORMAT_MSG
---

# KSDS3D_HRTF_FILTER_FORMAT_MSG structure


## -description


The KSDS3D_HRTF_FILTER_FORMAT_MSG structure specifies the filter format to use for a head-relative transfer function (HRTF).


## -syntax


````
typedef struct {
  KSDS3D_HRTF_FILTER_METHOD  FilterMethod;
  KSDS3D_HRTF_COEFF_FORMAT   CoeffFormat;
  KSDS3D_HRTF_FILTER_VERSION Version;
  ULONG                      Reserved;
} KSDS3D_HRTF_FILTER_FORMAT_MSG, *PKSDS3D_HRTF_FILTER_FORMAT_MSG;
````


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
For more information, see the description of the <b>MaxFilterSize</b> member of <a href="..\ksmedia\ns-ksmedia-ksds3d_hrtf_init_msg.md">KSDS3D_HRTF_INIT_MSG</a>.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_HRTF_FILTER_FORMAT_MSG structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

