---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET
title: tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET (ksmedia.h)
description: The KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure contains the parameters for the Camera Angle Offset Control property.
old-location: stream\kscamera_extendedprop_cameraoffset.htm
tech.root: stream
ms.assetid: D6C03D60-9FC4-4EF1-A7DD-4A91990D5CF1
ms.date: 04/23/2018
keywords: ["tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure"]
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, KSCAMERA_EXTENDEDPROP_CAMERAOFFSET, KSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_CAMERAOFFSET, ksmedia/PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET, stream.kscamera_extendedprop_cameraoffset, tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET"
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_CAMERAOFFSET"
 - "KSCAMERA_EXTENDEDPROP_CAMERAOFFSET"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- KSCAMERA_EXTENDEDPROP_CAMERAOFFSET
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_CAMERAOFFSET, *PKSCAMERA_EXTENDEDPROP_CAMERAOFFSET
---

# tagKSCAMERA_EXTENDEDPROP_CAMERAOFFSET structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_CAMERAOFFSET</b> structure contains the parameters for the <i>Camera Angle Offset Control</i> property. The members contain read-only values for the pitch and yaw angle of the camera position.  The pitch/yaw angle is defined to be an offset from horizontal and vertical axis.


## -struct-fields




### -field PitchAngle

The angle offset of the camera look direction from the horizontal axis of the camera facing direction.


### -field YawAngle

The angle offset of the camera look direction from the vertical axis of the camera facing direction.


### -field Flag

Reserved. Set to 0.


### -field Reserved

Reserved. Set to 0.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_extendedprop_header">KSCAMERA_EXTENDEDPROP_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-cameraangleoffset">KSPROPERTY_CAMERACONTROL_EXTENDED_CAMERAANGLEOFFSET</a>
 

 

