---
UID: NS:ksmedia._KS_DVD_YCrCb
title: "_KS_DVD_YCrCb"
author: windows-driver-content
description: The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace.
old-location: stream\ks_dvd_ycrcb.htm
old-project: stream
ms.assetid: 78010e49-ad09-4eb3-bb48-17040737a0a0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ksmedia/KS_DVD_YCrCb, stream.ks_dvd_ycrcb, KS_DVD_YCrCb structure [Streaming Media Devices], KS_DVD_YCrCb, PKS_DVD_YCrCb structure pointer [Streaming Media Devices], _KS_DVD_YCrCb, dvdref_559830d7-6f86-4a27-bc31-1e0e7928d7d4.xml, PKS_DVD_YCrCb, *PKS_DVD_YCrCb, ksmedia/PKS_DVD_YCrCb
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
-	KS_DVD_YCrCb
product: Windows
targetos: Windows
req.typenames: KS_DVD_YCrCb, *PKS_DVD_YCrCb
---

# _KS_DVD_YCrCb structure


## -description


The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace.


## -syntax


````
typedef struct _KS_DVD_YCrCb {
  UCHAR Reserved;
  UCHAR Y;
  UCHAR Cr;
  UCHAR Cb;
} KS_DVD_YCrCb, *PKS_DVD_YCrCb;
````


## -struct-fields




### -field Reserved

Reserved. Do not use.


### -field Y

Indicates the luminance (brightness) component of the color.


### -field Cr

Indicates the color-red (chrominance) component of the color.


### -field Cb

Indicates the color-blue (chrominance) component of the color.


## -remarks



The KS_DVD_YCrCb structure is used 




## -see-also

<a href="..\ksmedia\ns-ksmedia-_ks_dvd_yuv.md">KS_DVD_YUV</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVD_YCrCb structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

