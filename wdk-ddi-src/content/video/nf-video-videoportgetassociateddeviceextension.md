---
UID: NF:video.VideoPortGetAssociatedDeviceExtension
title: VideoPortGetAssociatedDeviceExtension function (video.h)
description: The VideoPortGetAssociatedDeviceExtension function returns the device extension for the parent of the specified device object.
old-location: display\videoportgetassociateddeviceextension.htm
tech.root: display
ms.assetid: 825e2b61-6b51-4553-88e1-0aff2e9e3cce
ms.date: 05/10/2018
keywords: ["VideoPortGetAssociatedDeviceExtension function"]
ms.keywords: VideoPortGetAssociatedDeviceExtension, VideoPortGetAssociatedDeviceExtension function [Display Devices], VideoPort_Functions_7116b537-1296-4136-b62c-ce5918eea10d.xml, display.videoportgetassociateddeviceextension, video/VideoPortGetAssociatedDeviceExtension
f1_keywords:
 - "video/VideoPortGetAssociatedDeviceExtension"
 - "VideoPortGetAssociatedDeviceExtension"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetAssociatedDeviceExtension
targetos: Windows
req.typenames: 
---

# VideoPortGetAssociatedDeviceExtension function


## -description


The <b>VideoPortGetAssociatedDeviceExtension</b> function returns the device extension for the parent of the specified device object.


## -parameters




### -param DeviceObject 
[in]
Is the device object of a child device.


## -returns



<b>VideoPortGetAssociatedDeviceExtension</b> returns a pointer to the device extension of <i>DeviceObject</i>'s parent.




## -remarks



The miniport driver of a child device can call this function to obtain a description of its parent through the parent's device extension.



