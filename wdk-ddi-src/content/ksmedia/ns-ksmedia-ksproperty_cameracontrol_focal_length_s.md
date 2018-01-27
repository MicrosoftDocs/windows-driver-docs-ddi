---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
title: KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
author: windows-driver-content
description: The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH property.
old-location: stream\ksproperty_cameracontrol_focal_length_s.htm
old-project: stream
ms.assetid: bf236fb9-8aa6-4f80-a8e3-85adfedd1f49
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure [Streaming Media Devices], ksmedia/PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, ksmedia/KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, vidcapstruct_d3d5d26e-e8be-4ce5-9a9a-03b125134bf7.xml, PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure pointer [Streaming Media Devices], *PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, stream.ksproperty_cameracontrol_focal_length_s, KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ksmedia.h
apiname: 
-	KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
product: Windows
targetos: Windows
req.typenames: *PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S
---

# KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure


## -description


The KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure returns filter-specific data requested using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564406">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a> property.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  LONG       lOcularFocalLength;
  LONG       lObjectiveFocalLengthMin;
  LONG       lObjectiveFocalLengthMax;
} KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S, *PKSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type. 


### -field lOcularFocalLength

Specifies a value of type LONG containing the focal length of the lens closest to the camera user.


### -field lObjectiveFocalLengthMin

Specifies a value of type LONG containing the minimum focal length of the lens closest to the camera subject.


### -field lObjectiveFocalLengthMax

Specifies a value of type LONG containing the maximum focal length of the lens closest to the camera subject.


## -remarks


If the camera has only one lens, these values can be used to represent zoom ratios. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff564406">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a>.



## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_cameracontrol_node_focal_length_s.md">KSPROPERTY_CAMERACONTROL_NODE_FOCAL_LENGTH_S</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564406">KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_FOCAL_LENGTH_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

