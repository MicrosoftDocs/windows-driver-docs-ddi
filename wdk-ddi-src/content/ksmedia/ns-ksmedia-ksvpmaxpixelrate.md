---
UID: NS:ksmedia.KSVPMAXPIXELRATE
title: KSVPMAXPIXELRATE
author: windows-driver-content
description: The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.
old-location: stream\ksvpmaxpixelrate.htm
old-project: stream
ms.assetid: 6510e732-b0ad-43c7-87a3-3630fdfd848d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSVPMAXPIXELRATE, KSVPMAXPIXELRATE, KSVPMAXPIXELRATE structure [Streaming Media Devices], PKSVPMAXPIXELRATE, PKSVPMAXPIXELRATE structure pointer [Streaming Media Devices], dvdref_c9ca0c83-e189-48b3-a798-95456c07ae0b.xml, ksmedia/KSVPMAXPIXELRATE, ksmedia/PKSVPMAXPIXELRATE, stream.ksvpmaxpixelrate"
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
-	KSVPMAXPIXELRATE
product:
- Windows
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



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566494">KSPROPERTY_VPCONFIG_MAXPIXELRATE</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566494">KSPROPERTY_VPCONFIG_MAXPIXELRATE</a>
 

 

