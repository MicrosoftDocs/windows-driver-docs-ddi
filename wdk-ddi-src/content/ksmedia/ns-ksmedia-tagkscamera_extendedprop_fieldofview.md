---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
title: tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
author: windows-driver-content
description: The Field of View Control property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.
old-location: stream\kscamera_extendedprop_fieldofview.htm
old-project: stream
ms.assetid: CC3FFC63-8404-4EA6-9738-F0A3C52585B8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, ksmedia/PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure pointer [Streaming Media Devices], KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, ksmedia/KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, KSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure [Streaming Media Devices], tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, stream.kscamera_extendedprop_fieldofview"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_FIELDOFVIEW
product: Windows
targetos: Windows
req.typenames: "*PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, KSCAMERA_EXTENDEDPROP_FIELDOFVIEW"
---

# tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure


## -description


The <i>Field of View Control</i> property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.


## -syntax


````
typedef struct _KSCAMERA_EXTENDEDPROP_FIELDOFVIEW {
  ULONG NormalizedFocalLengthX;
  ULONG NormalizedFocalLengthY;
  ULONG Flag;
  ULONG Reserved;
} KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, *PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW;
````


## -struct-fields




### -field NormalizedFocalLengthX

The horizontal focal length, in millimeters, normalized to a 35mm camera aperture size.


### -field NormalizedFocalLengthY

The vertical focal length, in millimeters, normalized to a 35mm camera aperture size.


### -field Flag

Reserved. Set to 0.


### -field Reserved

Reserved. Set to 0.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn567574">KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

