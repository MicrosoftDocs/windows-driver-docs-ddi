---
UID: NS:ksmedia.KSPROPERTY_DROPPEDFRAMES_CURRENT_S
title: KSPROPERTY_DROPPEDFRAMES_CURRENT_S
author: windows-driver-content
description: The KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure describes the dropped frame information from the minidriver.
old-location: stream\ksproperty_droppedframes_current_s.htm
old-project: stream
ms.assetid: 966af529-1725-4e80-9e67-cdb8666673f2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: vidcapstruct_ee78d2f2-c142-4d17-855d-7dc35589f271.xml, KSPROPERTY_DROPPEDFRAMES_CURRENT_S, PKSPROPERTY_DROPPEDFRAMES_CURRENT_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_DROPPEDFRAMES_CURRENT_S, stream.ksproperty_droppedframes_current_s, *PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure [Streaming Media Devices], PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, ksmedia/PKSPROPERTY_DROPPEDFRAMES_CURRENT_S
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
-	KSPROPERTY_DROPPEDFRAMES_CURRENT_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_DROPPEDFRAMES_CURRENT_S, KSPROPERTY_DROPPEDFRAMES_CURRENT_S"
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

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field PictureNumber

Specifies the current picture number provided by the minidriver. This value is the sum of the number of frames captured plus the number of frames dropped. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field DropCount

Specifies the count of dropped frames, which is provided by the minidriver. This counter increments whenever the minidriver was scheduled to capture a frame, but failed to do so, for example, because of buffer starvation. Initialize or update this value on transition into KSSTATE_ACQUIRE.


### -field AverageFrameSize

Specifies the average size of frames captured. This value is provided by the minidriver.


## -remarks


For more information about updating <b>PictureNumber</b> and <b>DropCount</b> see <a href="https://msdn.microsoft.com/0adea8fe-1669-4daf-a858-05e014f00a72">Capturing Video</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565135">KSPROPERTY_DROPPEDFRAMES_CURRENT</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567806">PROPSETID_VIDCAP_DROPPEDFRAMES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_DROPPEDFRAMES_CURRENT_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

