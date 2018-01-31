---
UID: NS:ksmedia.tagKSCAMERA_METADATA_PHOTOCONFIRMATION
title: tagKSCAMERA_METADATA_PHOTOCONFIRMATION
author: windows-driver-content
description: This structure contains the photo confirmation metadata information that is filled by the camera driver.
old-location: stream\kscamera_metadata_photoconfirmation.htm
old-project: stream
ms.assetid: FA3365DC-B604-468E-AACD-AC006D2B4EAF
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kscamera_metadata_photoconfirmation, KSCAMERA_METADATA_PHOTOCONFIRMATION structure [Streaming Media Devices], KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION, tagKSCAMERA_METADATA_PHOTOCONFIRMATION, ksmedia/PKSCAMERA_METADATA_PHOTOCONFIRMATION, ksmedia/KSCAMERA_METADATA_PHOTOCONFIRMATION, PKSCAMERA_METADATA_PHOTOCONFIRMATION structure pointer [Streaming Media Devices], PKSCAMERA_METADATA_PHOTOCONFIRMATION
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_METADATA_PHOTOCONFIRMATION
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION"
---

# tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure


## -description


This structure contains the photo confirmation metadata information that is filled by the camera driver.


## -syntax


````
typedef struct tagKSCAMERA_METADATA_PHOTOCONFIRMATION {
  KSCAMERA_METADATA_ITEMHEADER Header;
  ULONG                        PhotoConfirmationIndex;
  ULONG                        Reserved;
} KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION;
````


## -struct-fields




#### - Header

Contains the header information for the metadata item


#### - PhotoConfirmationIndex

Stores the index of the still confirmation frame. For single photo capture, this is always 0. For multishot, this corresponds to the index of the photo frame captured.


#### - Reserved

Reserved for future use.

