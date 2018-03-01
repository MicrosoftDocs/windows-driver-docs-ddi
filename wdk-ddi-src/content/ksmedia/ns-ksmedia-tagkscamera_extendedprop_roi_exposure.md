---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE
title: tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE
author: windows-driver-content
description: This structure contains the ROI info structure for exposure.
old-location: stream\kscamera_extendedprop_roi_exposure.htm
old-project: stream
ms.assetid: DE57E69E-6589-4336-BB3E-50715D6D5332
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, stream.kscamera_extendedprop_roi_exposure, tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE"
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
-	Ksmedia.h
api_name:
-	KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, *PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE
---

# tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE structure


## -description


This structure contains the ROI info structure for exposure.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE {
  KSCAMERA_EXTENDEDPROP_ROI_INFO ROIInfo;
  ULONGLONG                      Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_EXPOSURE, *PKSCAMERA_EXTENDEDPROP_ROI_EXPOSURE;
````


## -struct-fields




### -field ROIInfo

See the <a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_info.md">KSCAMERA_EXTENDEDPROP_ROI_INFO</a> structure for more information.


### -field Reserved

Reserved for future use.

