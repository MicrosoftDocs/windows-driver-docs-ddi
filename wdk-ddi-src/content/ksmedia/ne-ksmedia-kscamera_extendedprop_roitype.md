---
UID: NE:ksmedia.KSCAMERA_EXTENDEDPROP_ROITYPE
title: KSCAMERA_EXTENDEDPROP_ROITYPE
author: windows-driver-content
description: This enumeration contains the ROI types.
old-location: stream\kscamera_extendedprop_roitype.htm
old-project: stream
ms.assetid: 29458793-35DA-4CE4-AAD9-E1DD90C28E5C
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN, ksmedia/KSCAMERA_EXTENDEDPROP_ROITYPE_FACE, KSCAMERA_EXTENDEDPROP_ROITYPE, KSCAMERA_EXTENDEDPROP_ROITYPE enumeration [Streaming Media Devices], KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN, KSCAMERA_EXTENDEDPROP_ROITYPE_FACE, stream.kscamera_extendedprop_roitype, ksmedia/KSCAMERA_EXTENDEDPROP_ROITYPE
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
-	KSCAMERA_EXTENDEDPROP_ROITYPE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROITYPE
---

# KSCAMERA_EXTENDEDPROP_ROITYPE enumeration


## -description


This enumeration contains the ROI types.


## -syntax


````
typedef enum  { 
  KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN  = 0,
  KSCAMERA_EXTENDEDPROP_ROITYPE_FACE
} KSCAMERA_EXTENDEDPROP_ROITYPE;
````


## -enum-fields




### -field KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN

The ROI type is unknown.


### -field KSCAMERA_EXTENDEDPROP_ROITYPE_FACE

The ROI type is face.

