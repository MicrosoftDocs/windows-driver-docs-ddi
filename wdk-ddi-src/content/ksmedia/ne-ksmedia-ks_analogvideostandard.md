---
UID: NE:ksmedia.__unnamed_enum_60
title: KS_AnalogVideoStandard (ksmedia.h)
description: The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide.
old-location: stream\ks_analogvideostandard.htm
tech.root: stream
ms.assetid: 33efef2f-0734-416e-9f89-394a3dd344b8
ms.date: 04/23/2018
ms.keywords: KS_AnalogVideoStandard, KS_AnalogVideoStandard enumeration [Streaming Media Devices], KS_AnalogVideo_NTSC_433, KS_AnalogVideo_NTSC_M, KS_AnalogVideo_NTSC_M_J, KS_AnalogVideo_None, KS_AnalogVideo_PAL_60, KS_AnalogVideo_PAL_B, KS_AnalogVideo_PAL_D, KS_AnalogVideo_PAL_G, KS_AnalogVideo_PAL_H, KS_AnalogVideo_PAL_I, KS_AnalogVideo_PAL_M, KS_AnalogVideo_PAL_N, KS_AnalogVideo_PAL_N_COMBO, KS_AnalogVideo_SECAM_B, KS_AnalogVideo_SECAM_D, KS_AnalogVideo_SECAM_G, KS_AnalogVideo_SECAM_H, KS_AnalogVideo_SECAM_K, KS_AnalogVideo_SECAM_K1, KS_AnalogVideo_SECAM_L, KS_AnalogVideo_SECAM_L1, ksmedia/KS_AnalogVideoStandard, ksmedia/KS_AnalogVideo_NTSC_433, ksmedia/KS_AnalogVideo_NTSC_M, ksmedia/KS_AnalogVideo_NTSC_M_J, ksmedia/KS_AnalogVideo_None, ksmedia/KS_AnalogVideo_PAL_60, ksmedia/KS_AnalogVideo_PAL_B, ksmedia/KS_AnalogVideo_PAL_D, ksmedia/KS_AnalogVideo_PAL_G, ksmedia/KS_AnalogVideo_PAL_H, ksmedia/KS_AnalogVideo_PAL_I, ksmedia/KS_AnalogVideo_PAL_M, ksmedia/KS_AnalogVideo_PAL_N, ksmedia/KS_AnalogVideo_PAL_N_COMBO, ksmedia/KS_AnalogVideo_SECAM_B, ksmedia/KS_AnalogVideo_SECAM_D, ksmedia/KS_AnalogVideo_SECAM_G, ksmedia/KS_AnalogVideo_SECAM_H, ksmedia/KS_AnalogVideo_SECAM_K, ksmedia/KS_AnalogVideo_SECAM_K1, ksmedia/KS_AnalogVideo_SECAM_L, ksmedia/KS_AnalogVideo_SECAM_L1, stream.ks_analogvideostandard, vidcapstruct_90d60791-13e2-42ec-a641-6eee5bbf25fa.xml
ms.topic: enum
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
-	KS_AnalogVideoStandard
product:
- Windows
targetos: Windows
req.typenames: KS_AnalogVideoStandard
---

# KS_AnalogVideoStandard enumeration


## -description


The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide.


## -enum-fields




### -field KS_AnalogVideo_None

Specifies a digital sensor.


### -field KS_AnalogVideo_NTSC_M

Specifies the National Television Standards Committee (NTSC) "M" standard, at 7.5 IRE for black.


### -field KS_AnalogVideo_NTSC_M_J

Specifies the NTSC "M" standard that is used in Japan, at 0 IRE for black.


### -field KS_AnalogVideo_NTSC_433

Specifies the NTSC 433 standard


### -field KS_AnalogVideo_PAL_B

Specifies the Phase Alteration Line (PAL) "B" standard.


### -field KS_AnalogVideo_PAL_D

Specifies the PAL "D" standard.


### -field KS_AnalogVideo_PAL_G

Specifies the PAL "G" standard.


### -field KS_AnalogVideo_PAL_H

Specifies the PAL "H" standard.


### -field KS_AnalogVideo_PAL_I

Specifies the PAL "I" standard.


### -field KS_AnalogVideo_PAL_M

Specifies the PAL "M" standard.


### -field KS_AnalogVideo_PAL_N

Specifies the PAL "N" standard.


### -field KS_AnalogVideo_PAL_60

Specifies the PAL-60 standard.


### -field KS_AnalogVideo_SECAM_B

Specifies the Systeme Electronic Pour Couleur Avec Memoire (SECAM) "B" standard.


### -field KS_AnalogVideo_SECAM_D

Specifies the SECAM "D" standard.


### -field KS_AnalogVideo_SECAM_G

Specifies the SECAM "G" standard.


### -field KS_AnalogVideo_SECAM_H

Specifies the SECAM "H" standard.


### -field KS_AnalogVideo_SECAM_K

Specifies the SECAM "K" standard.


### -field KS_AnalogVideo_SECAM_K1

Specifies the SECAM "K1" standard.


### -field KS_AnalogVideo_SECAM_L

Specifies the SECAM "L" standard.


### -field KS_AnalogVideo_SECAM_L1

Specifies the SECAM "L1" standard.


### -field KS_AnalogVideo_PAL_N_COMBO

Specifies the combination PAL "N" standard (Argentina).


## -remarks



You can combine the values in the KS_AnalogVideoStandard enumeration with a bitwise OR  indicate support for multiple analog video standards.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565872">KSPROPERTY_TUNER_MODE_CAPS_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565918">KSPROPERTY_TUNER_STANDARD_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566047">KSPROPERTY_VIDEODECODER_CAPS_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567691">KS_TVTUNER_CHANGE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567692">KS_VBIINFOHEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567706">KS_VIDEO_STREAM_CONFIG_CAPS</a>
 

 

