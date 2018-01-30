---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
title: KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
author: windows-driver-content
description: Describes video stabilization control properties in the PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION camera control property set. This structure specifies property values that are used in requests to the camera driver.
old-location: stream\ksproperty_cameracontrol_videostabilization_mode_s.htm
old-project: stream
ms.assetid: 7cbf015c-4756-4d5c-a5fb-9cd8a5e0e3fd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure pointer [Streaming Media Devices], KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_AUTO, stream.ksproperty_cameracontrol_videostabilization_mode_s, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_OFF, PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_MEDIUM, ksmedia/PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_LOW, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_HIGH, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_AUTO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S"
---

# KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure


## -description


Describes video stabilization control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION</b> camera control property set. This structure specifies property values that are used in requests to the camera driver.


## -syntax


````
typedef struct {
  ULONG VideoStabilizationMode;
  ULONG Capabilities;
} KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S;
````


## -struct-fields




### -field VideoStabilizationMode

Indicates the selected video stabilization modes. This member has one of these possible values:


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_OFF

The video stabilization mode should not activate.


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_AUTO

The device automatically controls video stabilization.  This value is valid only if <b>KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_AUTO</b> is set in the <b>Capabilities</b> member.


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_LOW

Video stabilization is set at a low level.


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_MEDIUM

Video stabilization is set at a medium level.


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_HIGH

Video stabilization is set at a high level.


### -field Capabilities

Indicates whether the device and driver support setting video stabilization control automatically or manually. This member a bitwise <b>OR</b> of these possible values:


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_AUTO

The device and driver can automatically control video stabilization.


#### KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_MANUAL

The user can manually set video stabilization modes.


## -remarks


The video stabilization settings specified with this structure affect only the device and have no effect on applications' software video stabilization.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj156043">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE_PROPERTY</a>

<a href="..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_video_stabilization_mode.md">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

