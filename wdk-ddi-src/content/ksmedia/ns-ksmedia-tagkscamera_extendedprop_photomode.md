---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_PHOTOMODE
title: tagKSCAMERA_EXTENDEDPROP_PHOTOMODE (ksmedia.h)
description: The KSCAMERA_EXTENDEDPROP_PHOTOMODE structure contains the property data for the history frame counts in photo mode.
old-location: stream\kscamera_extendedprop_photomode.htm
tech.root: stream
ms.assetid: 96F920FC-43CE-4ACC-B880-9AD03B5D6009
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_PHOTOMODE, KSCAMERA_EXTENDEDPROP_PHOTOMODE, KSCAMERA_EXTENDEDPROP_PHOTOMODE structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_PHOTOMODE, PKSCAMERA_EXTENDEDPROP_PHOTOMODE structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_PHOTOMODE, ksmedia/PKSCAMERA_EXTENDEDPROP_PHOTOMODE, stream.kscamera_extendedprop_photomode, tagKSCAMERA_EXTENDEDPROP_PHOTOMODE"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- KSCAMERA_EXTENDEDPROP_PHOTOMODE
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_PHOTOMODE, *PKSCAMERA_EXTENDEDPROP_PHOTOMODE
---

# tagKSCAMERA_EXTENDEDPROP_PHOTOMODE structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_PHOTOMODE</b> structure contains the property data for the history  frame counts in photo mode. This structure is used when setting or retrieving the data for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn917959">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE</a> extended control property.


## -struct-fields




### -field RequestedHistoryFrames

The number of history frames to reserve by the driver. The value of <b>RequestedHistoryFrames</b> &lt;= <b>MaxHistoryFrames</b>.


### -field MaxHistoryFrames

Maximum number of history frames supported by the driver.


### -field SubMode

Not used. Set to 0.


### -field Reserved

Reserved. Set to 0.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn917959">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE</a>
 

 

