---
UID: NE:ksmedia.KSCAMERA_MetadataId
title: KSCAMERA_MetadataId
author: windows-driver-content
description: This enumeration contains identifiers for a metadata item.
old-location: stream\kscamera_metadataid.htm
old-project: stream
ms.assetid: 1CD1D065-9A96-42D5-807E-B439B4273920
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kscamera_metadataid, ksmedia/MetadataId_Standard_Start, ksmedia/MetadataId_Custom_Start, KSCAMERA_MetadataId, MetadataId_Standard_Start, ksmedia/MetadataId_Standard_End, ksmedia/MetadataId_PhotoConfirmation, KSCAMERA_MetadataId enumeration [Streaming Media Devices], ksmedia/KSCAMERA_MetadataId, MetadataId_Custom_Start, MetadataId_Standard_End, MetadataId_PhotoConfirmation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	KSCAMERA_MetadataId
product: Windows
targetos: Windows
req.typenames: KSCAMERA_MetadataId
---

# KSCAMERA_MetadataId enumeration


## -description


This enumeration contains identifiers for a metadata item.


## -syntax


````
typedef enum  { 
  MetadataId_Standard_Start     = 1,
  MetadataId_PhotoConfirmation  = MetadataId_Standard_Start,
  MetadataId_Standard_End       = MetadataId_PhotoConfirmation,
  MetadataId_Custom_Start       = 0x80000000
} KSCAMERA_MetadataId;
````


## -enum-fields




### -field MetadataId_Standard_Start

This represent the standard start metadata ID.


### -field MetadataId_PhotoConfirmation

This represents the photo confirmation metadata ID


### -field MetadataId_UsbVideoHeader



### -field MetadataId_CaptureStats



### -field MetadataId_CameraExtrinsics



### -field MetadataId_CameraIntrinsics



### -field MetadataId_FrameIllumination



### -field MetadataId_Standard_End

This represent the standard end  metadata ID.


### -field MetadataId_Custom_Start

This represents the lowest acceptable custom metadata ID.

