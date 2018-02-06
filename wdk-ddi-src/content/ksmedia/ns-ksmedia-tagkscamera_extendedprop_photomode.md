---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_PHOTOMODE
title: tagKSCAMERA_EXTENDEDPROP_PHOTOMODE
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_PHOTOMODE structure contains the property data for the history frame counts in photo mode.
old-location: stream\kscamera_extendedprop_photomode.htm
old-project: stream
ms.assetid: 96F920FC-43CE-4ACC-B880-9AD03B5D6009
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSCAMERA_EXTENDEDPROP_PHOTOMODE, stream.kscamera_extendedprop_photomode, PKSCAMERA_EXTENDEDPROP_PHOTOMODE structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_PHOTOMODE, *PKSCAMERA_EXTENDEDPROP_PHOTOMODE, PKSCAMERA_EXTENDEDPROP_PHOTOMODE, KSCAMERA_EXTENDEDPROP_PHOTOMODE structure [Streaming Media Devices], tagKSCAMERA_EXTENDEDPROP_PHOTOMODE, ksmedia/PKSCAMERA_EXTENDEDPROP_PHOTOMODE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_PHOTOMODE
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_PHOTOMODE, *PKSCAMERA_EXTENDEDPROP_PHOTOMODE
---

# tagKSCAMERA_EXTENDEDPROP_PHOTOMODE structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_PHOTOMODE</b> structure contains the property data for the history  frame counts in photo mode. This structure is used when setting or retrieving the data for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn917959">KSPROPERTY_CAMERACONTROL_EXTENDED_PHOTOMODE</a> extended control property.


## -syntax


````
typedef struct _KSCAMERA_EXTENDEDPROP_PHOTOMODE {
  ULONG RequestedHistoryFrames;
  ULONG MaxHistoryFrames;
  ULONG SubMode;
  ULONG Reserved;
} KSCAMERA_EXTENDEDPROP_PHOTOMODE, *PKSCAMERA_EXTENDEDPROP_PHOTOMODE;
````


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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_PHOTOMODE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

