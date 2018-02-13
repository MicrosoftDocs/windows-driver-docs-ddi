---
UID: NS:ksmedia._KSPROPERTY_SPPAL
title: "_KSPROPERTY_SPPAL"
author: windows-driver-content
description: The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display.
old-location: stream\ksproperty_sppal.htm
old-project: stream
ms.assetid: b6c50f2f-efc7-415f-895b-fcffb2575fe8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_SPPAL, dvdref_002f96c4-a499-4f93-8c3a-b083ed7a3339.xml, *PKSPROPERTY_SPPAL, stream.ksproperty_sppal, PKSPROPERTY_SPPAL structure pointer [Streaming Media Devices], PKSPROPERTY_SPPAL, _KSPROPERTY_SPPAL, KSPROPERTY_SPPAL structure [Streaming Media Devices], ksmedia/KSPROPERTY_SPPAL, ksmedia/PKSPROPERTY_SPPAL
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
-	KSPROPERTY_SPPAL
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_SPPAL, *PKSPROPERTY_SPPAL
---

# _KSPROPERTY_SPPAL structure


## -description


The KSPROPERTY_SPPAL structure is used to describe the palette of a subpicture display.


## -syntax


````
typedef struct _KSPROPERTY_SPPAL {
  KS_DVD_YUV sppal[16];
} KSPROPERTY_SPPAL, *PKSPROPERTY_SPPAL;
````


## -struct-fields




### -field sppal

Specifies an array of 16 YUV color values.


## -remarks



The KSPROPERTY_SPPAL structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565151">KSPROPERTY_DVDSUBPIC_PALETTE</a> property.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565151">KSPROPERTY_DVDSUBPIC_PALETTE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SPPAL structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

