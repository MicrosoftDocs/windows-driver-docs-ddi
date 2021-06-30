---
UID: NS:ksmedia.tagKSCAMERA_METADATA_PHOTOCONFIRMATION
title: tagKSCAMERA_METADATA_PHOTOCONFIRMATION (ksmedia.h)
description: This structure contains the photo confirmation metadata information that is filled by the camera driver.
tech.root: stream
ms.date: 06/24/2021
keywords: ["tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure"]
ms.keywords: "*PKSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION, KSCAMERA_METADATA_PHOTOCONFIRMATION structure [Streaming Media Devices], PKSCAMERA_METADATA_PHOTOCONFIRMATION, PKSCAMERA_METADATA_PHOTOCONFIRMATION structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_METADATA_PHOTOCONFIRMATION, ksmedia/PKSCAMERA_METADATA_PHOTOCONFIRMATION, stream.kscamera_metadata_photoconfirmation, tagKSCAMERA_METADATA_PHOTOCONFIRMATION"
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
req.typenames: KSCAMERA_METADATA_PHOTOCONFIRMATION, *PKSCAMERA_METADATA_PHOTOCONFIRMATION
f1_keywords:
 - tagKSCAMERA_METADATA_PHOTOCONFIRMATION
 - ksmedia/tagKSCAMERA_METADATA_PHOTOCONFIRMATION
 - PKSCAMERA_METADATA_PHOTOCONFIRMATION
 - ksmedia/PKSCAMERA_METADATA_PHOTOCONFIRMATION
 - KSCAMERA_METADATA_PHOTOCONFIRMATION
 - ksmedia/KSCAMERA_METADATA_PHOTOCONFIRMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - tagKSCAMERA_METADATA_PHOTOCONFIRMATION
 - PKSCAMERA_METADATA_PHOTOCONFIRMATION
 - KSCAMERA_METADATA_PHOTOCONFIRMATION
---

# tagKSCAMERA_METADATA_PHOTOCONFIRMATION structure

## -description

This structure contains the photo confirmation metadata information that is filled by the camera driver.

## -struct-fields

### -field Header

A [KSCAMERA_METADATA_ITEMHEADER](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_metadata_itemheader) structure that contains the metadata header information that is filled by the camera driver.

### -field PhotoConfirmationIndex

Stores the index of the still confirmation frame. For single photo capture, this is always 0. For multishot, this corresponds to the index of the photo frame captured.

### -field Reserved

Reserved for future use.
