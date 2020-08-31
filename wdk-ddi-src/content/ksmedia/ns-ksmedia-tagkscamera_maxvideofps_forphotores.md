---
UID: NS:ksmedia.tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES
title: tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES (ksmedia.h)
description: The KSCAMERA_MAXVIDEOFPS_FORPHOTORES structure contains the property data for maximum frame rate at a particular resolution for a camera supporting preview and capture.
old-location: stream\kscamera_maxvideofps_forphotores.htm
tech.root: stream
ms.assetid: 4230F7E1-DC36-4265-9E82-907EE82E9DFF
ms.date: 04/23/2018
keywords: ["tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES structure"]
ms.keywords: "*PKSCAMERA_MAXVIDEOFPS_FORPHOTORES, KSCAMERA_MAXVIDEOFPS_FORPHOTORES, KSCAMERA_MAXVIDEOFPS_FORPHOTORES structure [Streaming Media Devices], PKSCAMERA_MAXVIDEOFPS_FORPHOTORES, PKSCAMERA_MAXVIDEOFPS_FORPHOTORES structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_MAXVIDEOFPS_FORPHOTORES, ksmedia/PKSCAMERA_MAXVIDEOFPS_FORPHOTORES, stream.kscamera_maxvideofps_forphotores, tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
targetos: Windows
req.typenames: KSCAMERA_MAXVIDEOFPS_FORPHOTORES, *PKSCAMERA_MAXVIDEOFPS_FORPHOTORES
f1_keywords:
 - tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES
 - ksmedia/tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES
 - PKSCAMERA_MAXVIDEOFPS_FORPHOTORES
 - ksmedia/PKSCAMERA_MAXVIDEOFPS_FORPHOTORES
 - KSCAMERA_MAXVIDEOFPS_FORPHOTORES
 - ksmedia/KSCAMERA_MAXVIDEOFPS_FORPHOTORES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSCAMERA_MAXVIDEOFPS_FORPHOTORES
---

# tagKSCAMERA_MAXVIDEOFPS_FORPHOTORES structure


## -description

The <b>KSCAMERA_MAXVIDEOFPS_FORPHOTORES</b> structure contains the property data for maximum frame rate at a particular resolution for a camera supporting preview and capture. This structure is used when setting or retrieving the data for the <b>KSPROPERTY_CAMERACONTROL_EXTENDED_MAXVIDFPS_PHOTORES</b> extended control property.

## -struct-fields

### -field PhotoResWidth

The photo resolution width in pixels.

### -field PhotoResHeight

The photo resolution height in pixels.

### -field PreviewFPSNum

The numerator value of the preview frame rate.

### -field PreviewFPSDenom

The denominator value of the preview frame rate.

### -field CaptureFPSNum

The numerator value of the capture frame rate.

### -field CaptureFPSDenom

The denominator value of the capture frame rate.

## -remarks

When setting the property, using a KSPROPERTY_TYPE_SET  request, the <b>PhotoResWidth</b> and <b>PhotoResHeight</b> members are  supplied by the application based on the available photo media types.  The camera driver must retain this resolution information internally.  The preview and capture frame rate members must be ignored by the driver on KSPROPERTY_TYPE_SET requests.

For any subsequent KSPROPERTY_TYPE_GET request, the camera driver, based on the resolution provided in the earlier KSPROPERTY_TYPE_SET request, must provide the frame rates for the preview and capture streams.  Also, the camera driver must set the <b>PhotoResWidth</b> and <b>PhotoResHeight</b> to the resolution that was provided with the KSPROPERTY_TYPE_SET request.

If no KSPROPERTY_TYPE_SET request was made for the session, the camera driver set all the members of the <b>KSCAMERA_MAXVIDEOFPS_FORPHOTORES</b> structure to 0.

If preview or capture are not supported, such as the case when the camera is a dual pinned camera with only one video pin, it should use the <b>CaptureFPSNum</b> and <b>CaptureFPSDenom</b> members and set the <b>PreviewFPSNum</b> and <b>PreviewFPSDenom</b> members to 0.

If <b>KSCAMERA_EXTENDEDPROP_PHOTOMODE_SEQUENCE</b> is supported on the <i>Photo Mode Control</i> by the camera driver, this control is mandatory.

