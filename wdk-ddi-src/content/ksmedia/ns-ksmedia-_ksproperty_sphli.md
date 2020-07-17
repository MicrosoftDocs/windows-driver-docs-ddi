---
UID: NS:ksmedia._KSPROPERTY_SPHLI
title: _KSPROPERTY_SPHLI (ksmedia.h)
description: The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed.
old-location: stream\ksproperty_sphli.htm
tech.root: stream
ms.assetid: e1ee8d13-7f83-4020-9f34-4b2c3626685b
ms.date: 04/23/2018
keywords: ["_KSPROPERTY_SPHLI structure"]
ms.keywords: "*PKSPROPERTY_SPHLI, KSPROPERTY_SPHLI, KSPROPERTY_SPHLI structure [Streaming Media Devices], PKSPROPERTY_SPHLI, PKSPROPERTY_SPHLI structure pointer [Streaming Media Devices], _KSPROPERTY_SPHLI, dvdref_f6cc5797-e4f6-4973-abff-6b1bb9c0c637.xml, ksmedia/KSPROPERTY_SPHLI, ksmedia/PKSPROPERTY_SPHLI, stream.ksproperty_sphli"
f1_keywords:
 - "ksmedia/KSPROPERTY_SPHLI"
 - "KSPROPERTY_SPHLI"
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
- KSPROPERTY_SPHLI
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_SPHLI, *PKSPROPERTY_SPHLI
---

# _KSPROPERTY_SPHLI structure


## -description


The KSPROPERTY_SPHLI structure is used to describe a rectangle of subpicture or screen whose color or contrast is to be changed.


## -struct-fields




### -field HLISS

Indicates the highlight status of the current selection. A value of zero indicates that all highlights are invalid and the decoder should disable all highlights.


### -field Reserved

Reserved. Do not use.


### -field StartPTM

Indicates the start of presentation time.


### -field EndPTM

Indicates the end of presentation time.


### -field StartX

Indicates the start x-coordinate pixel of the current highlight button.


### -field StartY

Indicates the start y-coordinate pixel of the current highlight button.


### -field StopX

Indicates the ending x-coordinate pixel of the current highlight button.


### -field StopY

Indicates the ending y-coordinate pixel of the current highlight button.


### -field ColCon

Specifies the color/contrast of the highlight rectangle.


## -remarks



The KSPROPERTY_SPHLI structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdsubpic-hli">KSPROPERTY_DVDSUBPIC_HLI</a> property.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdsubpic-hli">KSPROPERTY_DVDSUBPIC_HLI</a>
 

 

