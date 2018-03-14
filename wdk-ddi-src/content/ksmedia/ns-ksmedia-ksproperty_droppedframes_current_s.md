---
UID: NS:ksmedia.KSPROPERTY_DROPPEDFRAMES_CURRENT_S
title: KSPROPERTY_DROPPEDFRAMES_CURRENT_S
author: windows-driver-content
description: The KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure describes the dropped frame information from the minidriver.
old-location: stream\ksproperty_droppedframes_current_s.htm
old-project: stream
ms.assetid: 966af529-1725-4e80-9e67-cdb8666673f2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, KSPROPERTY_DROPPEDFRAMES_CURRENT_S, KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure [Streaming Media Devices], PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, PKSPROPERTY_DROPPEDFRAMES_CURRENT_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_DROPPEDFRAMES_CURRENT_S, ksmedia/PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, stream.ksproperty_droppedframes_current_s, vidcapstruct_ee78d2f2-c142-4d17-855d-7dc35589f271.xml"
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
-	KSPROPERTY_DROPPEDFRAMES_CURRENT_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_DROPPEDFRAMES_CURRENT_S, *PKSPROPERTY_DROPPEDFRAMES_CURRENT_S
---

# KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure


## -description


The KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure describes the dropped frame information from the minidriver.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  LONGLONG   PictureNumber;
  LONGLONG   DropCount;
  ULONG      AverageFrameSize;
} KSPROPERTY_DROPPEDFRAMES_CURRENT_S, *PKSPROPERTY_DROPPEDFRAMES_CURRENT_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field PictureNumber

Specifies the current picture number provided by the minidriver. This value is the sum of the number of frames captured plus the number of frames dropped. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field DropCount

Specifies the count of dropped frames, which is provided by the minidriver. This counter increments whenever the minidriver was scheduled to capture a frame, but failed to do so, for example, because of buffer starvation. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field AverageFrameSize

Specifies the average size of frames captured. This value is provided by the minidriver.


## -remarks



For more information about updating <b>PictureNumber</b> and <b>DropCount</b> see <a href="https://msdn.microsoft.com/0adea8fe-1669-4daf-a858-05e014f00a72">Capturing Video</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567806">PROPSETID_VIDCAP_DROPPEDFRAMES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565135">KSPROPERTY_DROPPEDFRAMES_CURRENT</a>



 

 


