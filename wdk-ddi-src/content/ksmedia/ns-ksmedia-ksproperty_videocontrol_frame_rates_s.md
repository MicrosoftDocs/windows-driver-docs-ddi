---
UID: NS:ksmedia.KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S
title: KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOCONTROL_FRAME_RATES structure describes available frame rates in 100-nanosecond units.
old-location: stream\ksproperty_videocontrol_frame_rates_s.htm
old-project: stream
ms.assetid: fbd45594-a7cb-4376-b05c-d1e09462c78c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, stream.ksproperty_videocontrol_frame_rates_s, *PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, vidcapstruct_6f4d2262-8995-4b48-9029-595a7e7c1e15.xml, KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure pointer [Streaming Media Devices]
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
-	KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, *PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S
---

# KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure


## -description


The KSPROPERTY_VIDEOCONTROL_FRAME_RATES structure describes available frame rates in 100-nanosecond units.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      StreamIndex;
  ULONG      RangeIndex;
  SIZE       Dimensions;
} KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S, *PKSPROPERTY_VIDEOCONTROL_FRAME_RATES_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field StreamIndex

Contains the zero-based index of the stream.


### -field RangeIndex

Contains the zero-based index into the range list. The value at this location specifies the range in which frame rate information is being requested.


### -field Dimensions

Specifies the width and height of the image.


## -remarks



The minidriver should return a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure containing a list of the frame rates supported. These values should be expressed using type VT_I4.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEOCONTROL_FRAME_RATES_S structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

