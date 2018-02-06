---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_INFO
title: tagKSCAMERA_EXTENDEDPROP_ROI_INFO
author: windows-driver-content
description: This structure contains information about an ROI.
old-location: stream\kscamera_extendedprop_roi_info.htm
old-project: stream
ms.assetid: DAE013B7-7715-4B03-99F7-807306736C14
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKSCAMERA_EXTENDEDPROP_ROI_INFO, KSCAMERA_EXTENDEDPROP_ROI_INFO structure [Streaming Media Devices], stream.kscamera_extendedprop_roi_info, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_INFO, *PKSCAMERA_EXTENDEDPROP_ROI_INFO, KSCAMERA_EXTENDEDPROP_ROI_INFO, PKSCAMERA_EXTENDEDPROP_ROI_INFO, ksmedia/KSCAMERA_EXTENDEDPROP_ROI_INFO, PKSCAMERA_EXTENDEDPROP_ROI_INFO structure pointer [Streaming Media Devices]
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
-	KSCAMERA_EXTENDEDPROP_ROI_INFO
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_EXTENDEDPROP_ROI_INFO, KSCAMERA_EXTENDEDPROP_ROI_INFO"
---

# tagKSCAMERA_EXTENDEDPROP_ROI_INFO structure


## -description


This structure contains information about an ROI.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_INFO {
  RECT      Region;
  ULONGLONG Flags;
  LONG      Weight;
  LONG      RegionOfInterestType;
} KSCAMERA_EXTENDEDPROP_ROI_INFO, *PKSCAMERA_EXTENDEDPROP_ROI_INFO;
````


## -struct-fields




### -field Region

These are the relative coordinates in Q13 format on the frame that face detection is running.


### -field Flags

These are VIDEOPROCFLAG flags that indicate the op mode for the ISP control. For focus ROI, the default value is 0 representing focus region configuration without initiating a focus.


### -field Weight

This is the weight of the region (0-100).


### -field RegionOfInterestType

If the region is a face, this value is KSCAMERA_EXTENDEDPROP_ROITYPE_FACE. If the region is anything other than face, this value is KSCAMERA_EXTENDEDPROP_ROITYPE_UNKNOWN. For more information, see the <a href="..\ksmedia\ne-ksmedia-kscamera_extendedprop_roitype.md">KSCAMERA_EXTENDEDPROP_ROITYPE</a> enumeration.

