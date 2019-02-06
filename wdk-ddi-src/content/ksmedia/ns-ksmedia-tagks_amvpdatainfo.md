---
UID: NS:ksmedia.tagKS_AMVPDATAINFO
title: tagKS_AMVPDATAINFO (ksmedia.h)
description: The KS_AMVPDATAINFO structure is used to describe the properties of a video port.
old-location: stream\ks_amvpdatainfo.htm
tech.root: stream
ms.assetid: 4c217cf8-ca93-4e5d-8cbc-c56794f96d50
ms.date: 04/23/2018
ms.keywords: "*PKS_AMVPDATAINFO, KS_AMVPDATAINFO, KS_AMVPDATAINFO structure [Streaming Media Devices], PKS_AMVPDATAINFO, PKS_AMVPDATAINFO structure pointer [Streaming Media Devices], dvdref_e3126cb7-47dc-469b-b2ef-caefc04966cc.xml, ksmedia/KS_AMVPDATAINFO, ksmedia/PKS_AMVPDATAINFO, stream.ks_amvpdatainfo, tagKS_AMVPDATAINFO"
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
-	KS_AMVPDATAINFO
product:
- Windows
targetos: Windows
req.typenames: KS_AMVPDATAINFO, *PKS_AMVPDATAINFO
---

# tagKS_AMVPDATAINFO structure


## -description


The KS_AMVPDATAINFO structure is used to describe the properties of a video port.


## -struct-fields




### -field dwSize

Specifies the size of the structure, in bytes.


### -field dwMicrosecondsPerField

Specifies the time taken by each field, in microseconds (millionths of a second).


### -field amvpDimInfo

Describes the dimensional information of the video port, such as field and VBI dimensions.


### -field dwPictAspectRatioX

Indicates the picture aspect ratio in the horizontal dimension. For example, for a 16x9 aspect ratio this member would be 16.


### -field dwPictAspectRatioY

Indicates the picture aspect ratio in the vertical dimension. For example, for a 4x3 aspect ratio this member would be 3.


### -field bEnableDoubleClock

Specifies if the video port should enable double clocking. 


### -field bEnableVACT

Specifies if the video port should use an external VACT signal.


### -field bDataIsInterlaced

Indicates that the signal is interlaced.


### -field lHalfLinesOdd

Indicates the number of halflines in the odd field.


### -field bFieldPolarityInverted

Indicates if the device inverts the field polarity by default.


### -field dwNumLinesInVREF

Specifies the number of lines of data in VREF.


### -field lHalfLinesEven

Indicates the number of halflines in the even field.


### -field dwReserved1

Reserved for future use. Do not use.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566513">KSPROPERTY_VPCONFIG_VPDATAINFO</a>
 

 

