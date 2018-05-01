---
UID: NS:ksmedia._KSCAMERA_PROFILE_INFO
title: "_KSCAMERA_PROFILE_INFO"
author: windows-driver-content
description: The KSCAMERA_PROFILE_INFO structure is used to uniquely identify a given profile.
old-location: stream\kscamera_profile_info.htm
old-project: stream
ms.assetid: 566052ED-2FD8-46A9-8C4E-9FED660D93BF
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSCAMERA_PROFILE_INFO, KSCAMERA_PROFILE_INFO, KSCAMERA_PROFILE_INFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_INFO, PKSCAMERA_PROFILE_INFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_INFO, ksmedia/KSCAMERA_PROFILE_INFO, ksmedia/PKSCAMERA_PROFILE_INFO, stream.kscamera_profile_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSCAMERA_PROFILE_INFO
product: Windows
targetos: Windows
req.typenames: KSCAMERA_PROFILE_INFO, *PKSCAMERA_PROFILE_INFO
---

# _KSCAMERA_PROFILE_INFO structure


## -description


The <b>KSCAMERA_PROFILE_INFO</b> structure is used to uniquely identify a given profile.


## -struct-fields




### -field ProfileId

GUID representing a unique ID for the profile.  This GUID may be a unique IHV/OEM created GUID representing a custom profile or it may a pre-defined GUID.

<div class="alert"><b>Note</b>  This field must not be set to <b>KSCAMERAPROFILE_Legacy</b>.  The legacy profile must not be published by the camera driver.  The legacy profile ID will be sent to the camera driver during capture engine/media capture initialization if the application has not indicated that it can support profiles.  In such cases, the camera driver must revert its behavior to the Windows 8.1 mode of operation and expose only the reduced set media types along with the corresponding <b>KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_EXCLUSIVE_WITH_RECORD</b> and <b>KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_SEQUENCE_EXCLUSIVE_WITH_RECORD</b> capability bits indicating whether the camera driver is capable of supporting simultaneous recording/photo and/or recording/photo sequence within the reduced set media type.</div>
<div> </div>

### -field Index

Each profile within a given <b>ProfileId</b> group must have a unique <b>Index</b> value.  This allows any profile for a device to be uniquely identified with <b>ProfileId</b> + <b>Index</b>.


### -field PinCount

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/dn925220">KSCAMERA_PROFILE_PININFO</a> structures pointed to by <b>Pins</b>.  This value must be greater than 0.


### -field Pins

 An array of <b>KSCAMERA_PROFILE_PININFO</b> structures defining the supported media types on each of the pins of this profile. This field must not be <b>NULL</b>.

