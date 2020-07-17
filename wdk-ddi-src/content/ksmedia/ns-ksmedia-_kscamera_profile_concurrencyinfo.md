---
UID: NS:ksmedia._KSCAMERA_PROFILE_CONCURRENCYINFO
title: _KSCAMERA_PROFILE_CONCURRENCYINFO (ksmedia.h)
description: An array of KSCAMERA_PROFILE_CONCURRENCYINFO structures form the Camera.Concurrency parameter of the KSDEVICE_PROFILE_INFO structure (whose array size is specified by Camera.CountOfConcurrency parameter) indicating which profiles the profile identified in the KSCAMERA_PROFILE_INFO structure may run simultaneously on different cameras.
old-location: stream\kscamera_profile_concurrencyinfo.htm
tech.root: stream
ms.assetid: 4E0A9CE6-2FA0-46A5-B478-C088E5FF1BAD
ms.date: 04/23/2018
keywords: ["_KSCAMERA_PROFILE_CONCURRENCYINFO structure"]
ms.keywords: "*PKSCAMERA_PROFILE_CONCURRENCYINFO, KSCAMERA_PROFILE_CONCURRENCYINFO, KSCAMERA_PROFILE_CONCURRENCYINFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_CONCURRENCYINFO, PKSCAMERA_PROFILE_CONCURRENCYINFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_CONCURRENCYINFO, ksmedia/KSCAMERA_PROFILE_CONCURRENCYINFO, ksmedia/PKSCAMERA_PROFILE_CONCURRENCYINFO, stream.kscamera_profile_concurrencyinfo"
f1_keywords:
 - "ksmedia/KSCAMERA_PROFILE_CONCURRENCYINFO"
 - "KSCAMERA_PROFILE_CONCURRENCYINFO"
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
- ksmedia.h
api_name:
- KSCAMERA_PROFILE_CONCURRENCYINFO
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO
---

# _KSCAMERA_PROFILE_CONCURRENCYINFO structure


## -description


An array of <b>KSCAMERA_PROFILE_CONCURRENCYINFO</b> structures form the <b>Camera.Concurrency</b> parameter of   the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ksdevice_profile_info">KSDEVICE_PROFILE_INFO</a> structure (whose array size is specified by <b>Camera.CountOfConcurrency</b> parameter) indicating which profiles the profile identified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_kscamera_profile_info">KSCAMERA_PROFILE_INFO</a> structure may run simultaneously on different cameras.


## -struct-fields




### -field ReferenceGuid

Must be set to the <b>ReferenceGuid</b> of the <b>KSFILTER_DESCRIPTOR</b> which corresponds to the other device with which this profile is concurrent.


### -field Reserved

Unused.  Must be 0.


### -field ProfileCount

Number of profile IDs contained in the <b>Profiles</b> array.  Must be greater than 0.


### -field Profiles

This is an array of <b>KSCAMERA_PROFILE_INFO</b> structures that can be simultaneously used on the other camera device specified by the <b>ReferenceGuid</b>. This field must not be <b>NULL</b>.


## -remarks



Currently, an application has no knowledge as to whether it can attempt to stream from more than one camera until the attempt succeeds or fails.  In the case of web blogging scenario, this means the application will have to attempt to activate both streams before it paints the UI with a picture in picture video element.

For multiple applications, concurrency will not be sufficient to guarantee concurrent operation.  The concurrency information will not attempt to solve this scenario.  Instead, the existing camera yanking feature will be leveraged.

If both <b>Camera.CountOfConcurrency</b> and the <b>Camera.Concurrency</b> fields are 0 and <b>NULL</b> respectively, it indicates to the OS that the profile defined by the KSCAMERA_PROFILE_INFO is not a concurrent profile.



