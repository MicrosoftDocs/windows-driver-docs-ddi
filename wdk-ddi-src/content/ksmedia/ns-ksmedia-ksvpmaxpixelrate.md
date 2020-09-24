---
UID: NS:ksmedia.__unnamed_struct_156
title: KSVPMAXPIXELRATE (ksmedia.h)
description: The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.
old-location: stream\ksvpmaxpixelrate.htm
tech.root: stream
ms.assetid: 6510e732-b0ad-43c7-87a3-3630fdfd848d
ms.date: 04/30/2019
keywords: ["KSVPMAXPIXELRATE structure"]
ms.keywords: "*PKSVPMAXPIXELRATE, KSVPMAXPIXELRATE, KSVPMAXPIXELRATE structure [Streaming Media Devices], PKSVPMAXPIXELRATE, PKSVPMAXPIXELRATE structure pointer [Streaming Media Devices], dvdref_c9ca0c83-e189-48b3-a798-95456c07ae0b.xml, ksmedia/KSVPMAXPIXELRATE, ksmedia/PKSVPMAXPIXELRATE, stream.ksvpmaxpixelrate"
f1_keywords:
 - "ksmedia/KSVPMAXPIXELRATE"
 - "KSVPMAXPIXELRATE"
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
- KSVPMAXPIXELRATE
targetos: Windows
req.typenames: KSVPMAXPIXELRATE, *PKSVPMAXPIXELRATE
---

# KSVPMAXPIXELRATE structure


## -description


The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.


## -struct-fields




### -field Size

Specifies the dimension (width by height) of the video port.


### -field MaxPixelsPerSecond

Indicates the maximum pixel throughput for the selected image size.


### -field Reserved

Reserved. Do not use.


## -remarks



This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-vpconfig-maxpixelrate">KSPROPERTY_VPCONFIG_MAXPIXELRATE</a> property.




## -see-also




<a href="/windows-hardware/drivers/stream/ksproperty-vpconfig-maxpixelrate">KSPROPERTY_VPCONFIG_MAXPIXELRATE</a>
 

 