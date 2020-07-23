---
UID: NS:ksmedia.__unnamed_struct_120
title: KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S (ksmedia.h)
description: The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property.
old-location: stream\ksproperty_cameracontrol_focal_length_s.htm
tech.root: stream
ms.assetid: bf236fb9-8aa6-4f80-a8e3-85adfedd1f49
ms.date: 04/23/2018
keywords: ["KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, ksmedia/PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, stream.ksproperty_cameracontrol_focal_length_s, vidcapstruct_d3d5d26e-e8be-4ce5-9a9a-03b125134bf7.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S"
 - "KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, *PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
---

# KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure


## -description


The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-focal-length">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a> property.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field lOcularFocalLength

Specifies a value of type LONG containing the focal length of the lens closest to the camera user.


### -field lObjectiveFocalLengthMin

Specifies a value of type LONG containing the minimum focal length of the lens closest to the camera subject.


### -field lObjectiveFocalLengthMax

Specifies a value of type LONG containing the maximum focal length of the lens closest to the camera subject.


## -remarks



If the camera has only one lens, these values can be used to represent zoom ratios. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-focal-length">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-cameracontrol-focal-length">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_node_focal_length_s">KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-cameracontrol">PROPSETID_VIDCAP_CAMERACONTROL</a>
 

 

