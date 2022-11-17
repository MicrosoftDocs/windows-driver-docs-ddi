---
UID: NS:ksmedia._KSCAMERA_PROFILE_INFO
title: KSCAMERA_PROFILE_INFO (ksmedia.h)
description: The KSCAMERA_PROFILE_INFO structure is used to uniquely identify a given profile.
tech.root: stream
ms.date: 11/17/2022
keywords: ["KSCAMERA_PROFILE_INFO structure"]
ms.keywords: "*PKSCAMERA_PROFILE_INFO, KSCAMERA_PROFILE_INFO, KSCAMERA_PROFILE_INFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_INFO, PKSCAMERA_PROFILE_INFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_INFO, ksmedia/KSCAMERA_PROFILE_INFO, ksmedia/PKSCAMERA_PROFILE_INFO, stream.kscamera_profile_info"
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
targetos: Windows
req.typenames: KSCAMERA_PROFILE_INFO, *PKSCAMERA_PROFILE_INFO
f1_keywords:
 - _KSCAMERA_PROFILE_INFO
 - ksmedia/_KSCAMERA_PROFILE_INFO
 - PKSCAMERA_PROFILE_INFO
 - ksmedia/PKSCAMERA_PROFILE_INFO
 - KSCAMERA_PROFILE_INFO
 - ksmedia/KSCAMERA_PROFILE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - _KSCAMERA_PROFILE_INFO
 - PKSCAMERA_PROFILE_INFO
 - KSCAMERA_PROFILE_INFO
---

## -description

The **KSCAMERA_PROFILE_INFO** structure is used to uniquely identify a given profile.

## -struct-fields

### -field ProfileId

GUID representing a unique ID for the profile.  This GUID may be a unique IHV/OEM created GUID representing a custom profile or it may a pre-defined GUID.

> [!NOTE]
> This field must not be set to **KSCAMERAPROFILE_Legacy**.  The legacy profile must not be published by the camera driver.  The legacy profile ID will be sent to the camera driver during capture engine/media capture initialization if the application has not indicated that it can support profiles.  In such cases, the camera driver must revert its behavior to the Windows 8.1 mode of operation and expose only the reduced set media types along with the corresponding **KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_EXCLUSIVE_WITH_RECORD** and **KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_SEQUENCE_EXCLUSIVE_WITH_RECORD** capability bits indicating whether the camera driver is capable of supporting simultaneous recording/photo and/or recording/photo sequence within the reduced set media type.

### -field Index

Each profile within a given **ProfileId** group must have a unique **Index** value.  This allows any profile for a device to be uniquely identified with **ProfileId** + **Index**.

### -field PinCount

The number of [**KSCAMERA_PROFILE_PININFO**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_kscamera_profile_pininfo) structures pointed to by **Pins**.  This value must be greater than 0.

### -field Pins

 An array of **KSCAMERA_PROFILE_PININFO** structures defining the supported media types on each of the pins of this profile. This field must not be **NULL**.
