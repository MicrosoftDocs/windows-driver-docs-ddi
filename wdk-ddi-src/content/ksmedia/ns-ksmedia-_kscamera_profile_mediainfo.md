---
UID: NS:ksmedia._KSCAMERA_PROFILE_MEDIAINFO
title: _KSCAMERA_PROFILE_MEDIAINFO (ksmedia.h)
description: This structure contains the relevant media type information presented for each camera profile.
old-location: stream\kscamera_profile_mediainfo.htm
tech.root: stream
ms.assetid: 55B9F032-A3F5-434E-9EB6-CB832DC0EB45
ms.date: 04/23/2018
keywords: ["KSCAMERA_PROFILE_MEDIAINFO structure"]
ms.keywords: "*PKSCAMERA_PROFILE_MEDIAINFO, KSCAMERA_PROFILE_MEDIAINFO, KSCAMERA_PROFILE_MEDIAINFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_MEDIAINFO, PKSCAMERA_PROFILE_MEDIAINFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_MEDIAINFO, ksmedia/KSCAMERA_PROFILE_MEDIAINFO, ksmedia/PKSCAMERA_PROFILE_MEDIAINFO, stream.kscamera_profile_mediainfo"
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
targetos: Windows
req.typenames: KSCAMERA_PROFILE_MEDIAINFO, *PKSCAMERA_PROFILE_MEDIAINFO
f1_keywords:
 - _KSCAMERA_PROFILE_MEDIAINFO
 - ksmedia/_KSCAMERA_PROFILE_MEDIAINFO
 - PKSCAMERA_PROFILE_MEDIAINFO
 - ksmedia/PKSCAMERA_PROFILE_MEDIAINFO
 - KSCAMERA_PROFILE_MEDIAINFO
 - ksmedia/KSCAMERA_PROFILE_MEDIAINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSCAMERA_PROFILE_MEDIAINFO
---

# _KSCAMERA_PROFILE_MEDIAINFO structure


## -description

This structure contains the relevant media type information presented for each camera profile.

## -struct-fields

### -field Resolution

The X (horizontal) and Y (vertical) frame size in pixels.

### -field Resolution.X

### -field Resolution.Y

### -field MaxFrameRate

The numerator/denominator ratio of frame rate (for example, 30 / 1 = 30fps).  This frame rate represents the maximum frame rate of the specified resolution under ideal lighting conditions.  Actual frame rate may be lower than this value.

For photo media information, if photo sequence cannot be enabled because of hardware constraints for the given photo resolution, the frame rate must be set to 0 (numerator=0, denominator=0).  This will inform the application layer that photo sequence control will be rejected by the driver when that particular photo media type is selected.

### -field MaxFrameRate.Numerator

### -field MaxFrameRate.Denominator

### -field Flags

The  bitwise OR of one or more of the following flags:

<ul>
<li>KSCAMERAPROFILE_FLAGS_VIDEOHDRWhen the video HDR flag is set for the media info, for that media setting, video HDR may be enabled for the record stream.

This flag may not be set for media info on the photo pin.

</li>
<li>KSCAMERAPROFILE_FLAGS_VARIABLEPHOTOSEQUENCEWhen the Variable Photo Sequence flag is set for the media info, VPS support is available even if the photo media info does not provide a frame rate.

If this flag is set and the frame rate is non-zero, for that photo media info, VPS and Photo Sequence is available.

If this flag is set and the frame rate is zero, for that photo media info, VPS is available but not Photo Sequence.

If this flag is not set and the  frame rate is non-zero, for that photo media info, VPS is not available but Photo Sequence is available.

If  this flag is not set and the frame rate is zero, neither VPS nor Photo Sequence is available for that media info.

This flag may only be set for media info on the photo pin.  Presence of this flag on non-photo pin media info will result in the profile set being rejected.

</li>
</ul>

### -field Data0

Reserved. Must be set to 0.

### -field Data1

Reserved. Must be set to 0.

### -field Data2

Reserved. Must be set to 0.

### -field Data3

Reserved. Must be set to 0.

