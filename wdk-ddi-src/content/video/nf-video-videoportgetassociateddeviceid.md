---
UID: NF:video.VideoPortGetAssociatedDeviceID
title: VideoPortGetAssociatedDeviceID function (video.h)
description: The VideoPortGetAssociatedDeviceID function obtains the child ID for a specified device object.
old-location: display\videoportgetassociateddeviceid.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortGetAssociatedDeviceID function"]
ms.keywords: VideoPortGetAssociatedDeviceID, VideoPortGetAssociatedDeviceID function [Display Devices], VideoPort_Functions_56a3fa57-fd1a-4b45-8de7-ee9450a525f4.xml, display.videoportgetassociateddeviceid, video/VideoPortGetAssociatedDeviceID
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortGetAssociatedDeviceID
 - video/VideoPortGetAssociatedDeviceID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortGetAssociatedDeviceID
---

# VideoPortGetAssociatedDeviceID function


## -description

The <b>VideoPortGetAssociatedDeviceID</b> function obtains the child ID for a specified device object.

## -parameters

### -param DeviceObject 

[in]
Pointer to the child device object, a <a href="/windows-hardware/drivers/">PDO</a>.

## -returns

<b>VideoPortGetAssociatedDeviceID</b> returns the child ID for the given device object.

## -remarks

<b>VideoPortGetAssociatedDeviceID</b> can be used to obtain the child ID for a child device object. For example, this is useful with <a href="/windows-hardware/drivers/">I2C</a>. See <a href="/windows-hardware/drivers/display/using-i2c-to-communicate-with-a-child-device">Using I2C to Communicate with a Child Device</a> for more information.
