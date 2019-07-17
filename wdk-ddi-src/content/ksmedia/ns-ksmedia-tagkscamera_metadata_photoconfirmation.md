---
UID: NS:ksmedia.tagKSCAMERA_METADATA_PHOTOCONFIRMATION
title: tagKSCAMERA_METADATA_PHOTOCONFIRMATION (ksmedia.h)
description: This structure contains the photo confirmation metadata information that is filled by the camera driver.
old-location: stream\kscamera_metadata_photoconfirmation.htm
tech.root: stream
ms.assetid: FA3365DC-B604-468E-AACD-AC006D2B4EAF
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION structure [Streaming Media Devices], PKSCAMERA_METADATA_PHOTOCONFIRMATION, PKSCAMERA_METADATA_PHOTOCONFIRMATION structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_METADATA_PHOTOCONFIRMATION, ksmedia/PKSCAMERA_METADATA_PHOTOCONFIRMATION, stream.kscamera_metadata_photoconfirmation, tagKSCAMERA_METADATA_PHOTOCONFIRMATION"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_METADATA_PHOTOCONFIRMATION"
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
- KSCAMERA_METADATA_PHOTOCONFIRMATION
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION
---

# tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure


## -description


This structure contains the photo confirmation metadata information that is filled by the camera driver.


## -struct-fields




### -field Header

Contains the header information for the metadata item


### -field PhotoConfirmationIndex

Stores the index of the still confirmation frame. For single photo capture, this is always 0. For multishot, this corresponds to the index of the photo frame captured.


### -field Reserved

Reserved for future use.

