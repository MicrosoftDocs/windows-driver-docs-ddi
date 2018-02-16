---
UID: NS:ksmedia.KSVPMAXPIXELRATE
title: KSVPMAXPIXELRATE
author: windows-driver-content
description: The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.
old-location: stream\ksvpmaxpixelrate.htm
old-project: stream
ms.assetid: 6510e732-b0ad-43c7-87a3-3630fdfd848d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/PKSVPMAXPIXELRATE, *PKSVPMAXPIXELRATE, ksmedia/KSVPMAXPIXELRATE, dvdref_c9ca0c83-e189-48b3-a798-95456c07ae0b.xml, KSVPMAXPIXELRATE, KSVPMAXPIXELRATE structure [Streaming Media Devices], stream.ksvpmaxpixelrate, PKSVPMAXPIXELRATE, PKSVPMAXPIXELRATE structure pointer [Streaming Media Devices]
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
-	KSVPMAXPIXELRATE
product: Windows
targetos: Windows
req.typenames: "*PKSVPMAXPIXELRATE, KSVPMAXPIXELRATE"
---

# KSVPMAXPIXELRATE structure


## -description


The KSVPMAXPIXELRATE structure is used to describe the maximum pixel rate of a video port.


## -syntax


````
typedef struct {
  AMVPSIZE Size;
  DWORD    MaxPixelsPerSecond;
  DWORD    Reserved;
} KSVPMAXPIXELRATE, *PKSVPMAXPIXELRATE;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSVPMAXPIXELRATE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

