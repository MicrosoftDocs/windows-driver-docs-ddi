---
UID: NS:ksmedia._KSCAMERA_PROFILE_PININFO
title: _KSCAMERA_PROFILE_PININFO (ksmedia.h)
description: This structure specifies the available list of media types for each of the camera driver pins.
old-location: stream\kscamera_profile_pininfo.htm
tech.root: stream
ms.assetid: 09B7D454-D28C-4E3F-9FF3-0DD595CDB90A
ms.date: 04/23/2018
keywords: ["_KSCAMERA_PROFILE_PININFO structure"]
ms.keywords: "*PKSCAMERA_PROFILE_PININFO, KSCAMERA_PROFILE_PININFO, KSCAMERA_PROFILE_PININFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_PININFO, PKSCAMERA_PROFILE_PININFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_PININFO, ksmedia/KSCAMERA_PROFILE_PININFO, ksmedia/PKSCAMERA_PROFILE_PININFO, stream.kscamera_profile_pininfo"
f1_keywords:
 - "ksmedia/KSCAMERA_PROFILE_PININFO"
req.header: ksmedia.h
req.include-header: 
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
- Ksmedia.h
api_name:
- KSCAMERA_PROFILE_PININFO
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_PROFILE_PININFO, *PKSCAMERA_PROFILE_PININFO
---

# _KSCAMERA_PROFILE_PININFO structure


## -description


This structure specifies the available list of media types for each of the camera driver pins.


## -struct-fields




### -field PinCategory

This is the PINNAME category corresponding to Capture, Preview or Still image pin.  For Windows 10, the only supported pin categories are:  PINNAME_VIDEO_CAPTURE, PINNAME_VIDEO_PREVIEW, PINNAME_VIDEO_STILL.  All other categories will result in an STATUS_INVALID_PARAMETER error.


### -field PinIndex

 


### -field ProfileSensorType

 


### -field Reserved

Unused. Must be 0.


### -field MediaInfoCount

Array size of KSCAMERA_PROFILE_MEDIAINFO structures specified in the MediaInfos field.


### -field MediaInfos

Array of KSCAMERA_PROFILE_MEDIAINFO structures.

