---
UID: NS:ksmedia.tagKSCAMERA_METADATA_ITEMHEADER
title: tagKSCAMERA_METADATA_ITEMHEADER
author: windows-driver-content
description: This structure contains the metadata header information that is filled by the camera driver.
old-location: stream\kscamera_metadata_itemheader.htm
old-project: stream
ms.assetid: B4AC04D7-9F98-41F1-A38D-927F3F3A7699
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KSCAMERA_METADATA_ITEMHEADER structure [Streaming Media Devices], KSCAMERA_METADATA_ITEMHEADER, tagKSCAMERA_METADATA_ITEMHEADER, PKSCAMERA_METADATA_ITEMHEADER structure pointer [Streaming Media Devices], PKSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER, ksmedia/PKSCAMERA_METADATA_ITEMHEADER, stream.kscamera_metadata_itemheader, ksmedia/KSCAMERA_METADATA_ITEMHEADER
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
-	ksmedia.h
apiname:
-	KSCAMERA_METADATA_ITEMHEADER
product: Windows
targetos: Windows
req.typenames: KSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER
---

# tagKSCAMERA_METADATA_ITEMHEADER structure


## -description


This structure contains the metadata header information that is filled by the camera driver.


## -syntax


````
typedef struct tagKSCAMERA_METADATA_ITEMHEADER {
  ULONG MetadataId;
  ULONG Size;
} KSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER;
````


## -struct-fields




### -field MetadataId

The identifier for the metadata item. This can be a standard identifier as defined in the <a href="..\ksmedia\ne-ksmedia-kscamera_metadataid.md">KSCAMERA_MetadataId</a> enumeration or any custom metadata identifier that starts from MetadataId_Custom_Start (0x80000000).


### -field Size

Set to <b>sizeof(KSCAMERA_METADATA_ITEMHEADER)</b> + the size of the metadata payload that follows.


## -remarks



This structure along with the metadata payload that follows must be 8-byte aligned.



