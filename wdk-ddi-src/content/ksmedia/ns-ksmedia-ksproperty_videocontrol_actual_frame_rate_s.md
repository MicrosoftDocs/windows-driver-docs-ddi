---
UID: NS:ksmedia.KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
title: KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests.
old-location: stream\ksproperty_videocontrol_actual_frame_rate_s.htm
old-project: stream
ms.assetid: 98b6c085-d7d0-47e4-acea-a272487f20c2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, ksmedia/PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, stream.ksproperty_videocontrol_actual_frame_rate_s, vidcapstruct_7ae44134-3ba1-4419-9290-c305f345e29c.xml"
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
-	KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S, *PKSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S
---

# KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure


## -description


The KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE_S structure describes actual frame rate information in response to KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE property requests.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field StreamIndex

Contains the zero-based index of the stream.


### -field RangeIndex

Contains the zero-based index into the range list. The value contained at this location specifies the range in which frame rate information is being requested.


### -field Dimensions

Specifies the width and height of the image.


### -field CurrentActualFrameRate

Specifies the actual frame rate for the specified stream and range. Frame rate values are expressed in 100-nanosecond units.


### -field CurrentMaxAvailableFrameRate

Specifies the maximum frame rate for the specified stream and range. Frame rate values are expressed in 100-nanosecond units.


## -remarks



The minidriver should return STATUS_NOT_SUPPORTED if the pin is not open.




## -see-also

<<<<<<< HEAD



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>
=======
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566024">KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE</a>
>>>>>>> parent of 2d896a8e266... Added changes



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566024">KSPROPERTY_VIDEOCONTROL_ACTUAL_FRAME_RATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568120">PROPSETID_VIDCAP_VIDEOCONTROL</a>
 

 

