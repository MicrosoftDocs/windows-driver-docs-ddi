---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
title: tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION (ksmedia.h)
description: The EV Compensation Control provides for exposure control that is adjusted by increments of EV compensation steps.
old-location: stream\kscamera_extendedprop_evcompensation.htm
tech.root: stream
ms.assetid: C9CF39F2-5081-4B99-BFD1-9F7130B27369
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, ksmedia/PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, stream.kscamera_extendedprop_evcompensation, tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_EVCOMPENSATION"
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
- KSCAMERA_EXTENDEDPROP_EVCOMPENSATION
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, *PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
---

# tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure


## -description


The <i>EV Compensation Control</i> provides for exposure control that is adjusted by increments of EV compensation steps.


## -struct-fields




### -field Mode

Not used. Set to 0.


### -field Min

The minimum EV compensation supported. This is an absolute EV value.


### -field Max

The maximum EV compensation supported. This is an absolute EV value.


### -field Value

EV Compensation in units of steps  selected in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_extendedprop_header">KSCAMERA_EXTENDEDPROP_HEADER</a>.


### -field Reserved

Reserved.


## -remarks



<b>Value</b> is assigned a stepping increment. For example, if <b>Min</b> = -2, <b>Max</b> = 2 and the compensation stepping is set as one third step (incremented in units of 1/3 EV compensation), the valid values of EV compensation are -2, -1 2/3, -1 1/3, -1, -2/3, -1/3, 0, 1/3, 2/3, 1, 1 1/3, 1 2/3, and 2.  This corresponds to the <b>Value</b> field as -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6. As an example, if  <b>Value</b> = -6, then EV compensation = -2, or (-6 * 1/3) = -2.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_extendedprop_header">KSCAMERA_EXTENDEDPROP_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-extended-evcompensation">KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION</a>
 

 

