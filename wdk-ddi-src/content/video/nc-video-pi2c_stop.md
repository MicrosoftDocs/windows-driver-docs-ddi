---
UID: NC:video.PI2C_STOP
title: PI2C_STOP (video.h)
description: The I2CStop function ends I2C communication.
old-location: display\i2cstop.htm
tech.root: display
ms.assetid: 535e1603-08e3-4ad1-b4e5-f0368b7d3e71
ms.date: 05/10/2018
ms.keywords: I2CStop, I2CStop callback function [Display Devices], PI2C_STOP, PI2C_STOP callback, VideoPort_Functions_736a5ce6-846f-4c8c-b851-b65c365bba71.xml, display.i2cstop, video/I2CStop
ms.topic: callback
f1_keywords:
 - "video/I2CStop"
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- I2CStop
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI2C_STOP callback function


## -description


The <i>I2CStop</i> function ends <a href="https://docs.microsoft.com/windows-hardware/drivers/">I2C</a> communication.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_i2c_callbacks">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


## -returns



<i>I2CStop</i> returns <b>TRUE</b> if I²C communication was successfully stopped, and <b>FALSE</b> otherwise.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a>
 

 

