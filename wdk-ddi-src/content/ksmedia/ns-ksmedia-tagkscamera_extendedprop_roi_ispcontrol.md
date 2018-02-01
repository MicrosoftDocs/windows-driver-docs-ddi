---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL
title: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL
author: windows-driver-content
description: This structure contains information for an ROI ISP control.
old-location: stream\kscamera_extendedprop_roi_ispcontrol.htm
old-project: stream
ms.assetid: 49EAB8F3-35B9-4F99-A7B8-66B582B228B1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kscamera_extendedprop_roi_ispcontrol, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL structure pointer [Streaming Media Devices], ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, ksmedia/KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL
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
-	KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL"
---

# tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL structure


## -description


This structure contains information for an ROI ISP control.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL {
  ULONG ControlId;
  ULONG ROICount;
  ULONG Result;
  ULONG Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL;
````


## -struct-fields




### -field ControlId

The ISP control ID. The following are valid values for this field. These values are defined in ksmedia.h.
<ul>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE

</li>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE

</li>
<li>
KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE

</li>
</ul>

### -field ROICount

The number of ROIs associated with this ISP control.


### -field Result

The error results of the last SET operation for this ISP control.


### -field Reserved

Reserved for future use.

