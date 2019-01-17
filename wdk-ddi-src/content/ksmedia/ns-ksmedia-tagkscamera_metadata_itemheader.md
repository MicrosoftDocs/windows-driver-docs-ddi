---
UID: NS:ksmedia.tagKSCAMERA_METADATA_ITEMHEADER
title: tagKSCAMERA_METADATA_ITEMHEADER
description: This structure contains the metadata header information that is filled by the camera driver.
old-location: stream\kscamera_metadata_itemheader.htm
tech.root: stream
ms.assetid: B4AC04D7-9F98-41F1-A38D-927F3F3A7699
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_METADATA_ITEMHEADER, KSCAMERA_METADATA_ITEMHEADER, KSCAMERA_METADATA_ITEMHEADER structure [Streaming Media Devices], PKSCAMERA_METADATA_ITEMHEADER, PKSCAMERA_METADATA_ITEMHEADER structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_METADATA_ITEMHEADER, ksmedia/PKSCAMERA_METADATA_ITEMHEADER, stream.kscamera_metadata_itemheader, tagKSCAMERA_METADATA_ITEMHEADER"
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
-	KSCAMERA_METADATA_ITEMHEADER
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER
---

# tagKSCAMERA_METADATA_ITEMHEADER structure


## -description


This structure contains the metadata header information that is filled by the camera driver.


## -struct-fields




### -field MetadataId

The identifier for the metadata item. This can be a standard identifier as defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925181">KSCAMERA_MetadataId</a> enumeration or any custom metadata identifier that starts from MetadataId_Custom_Start (0x80000000).


### -field Size

Set to <b>sizeof(KSCAMERA_METADATA_ITEMHEADER)</b> + the size of the metadata payload that follows.


## -remarks



This structure along with the metadata payload that follows must be 8-byte aligned.



