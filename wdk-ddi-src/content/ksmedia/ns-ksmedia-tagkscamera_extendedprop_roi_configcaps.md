---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
title: tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
author: windows-driver-content
description: This structure contains the capabilities for an ROI control.
old-location: stream\kscamera_extendedprop_roi_configcaps.htm
old-project: stream
ms.assetid: BAC5B134-22F5-4BC9-BBD6-6AF3C934510B
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, stream.kscamera_extendedprop_roi_configcaps, tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS"
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
-	KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS
---

# tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS structure


## -description


This structure contains the capabilities for an ROI control.


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

### -field MaxNumberOfROIs

The maximum ROIs supported for this ISO control.


### -field Capability

The capabilities for this ISP control.

