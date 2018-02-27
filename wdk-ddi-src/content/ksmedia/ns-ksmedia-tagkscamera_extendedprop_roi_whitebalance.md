---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
title: tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
author: windows-driver-content
description: This structure contains the ROI info structure for white balance.
old-location: stream\kscamera_extendedprop_roi_whitebalance.htm
old-project: stream
ms.assetid: 16BDC61E-390C-4D79-A8D0-049404974733
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, stream.kscamera_extendedprop_roi_whitebalance, tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE"
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
-	KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, *PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE
---

# tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE structure


## -description


This structure contains the ROI info structure for white balance.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE {
  KSCAMERA_EXTENDEDPROP_ROI_INFO ROIInfo;
  ULONGLONG                      Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE, *PKSCAMERA_EXTENDEDPROP_ROI_WHITEBALANCE;
````


## -struct-fields




### -field ROIInfo

See the <a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_info.md">KSCAMERA_EXTENDEDPROP_ROI_INFO</a> structure for more information.


### -field Reserved

Reserved for future use.

