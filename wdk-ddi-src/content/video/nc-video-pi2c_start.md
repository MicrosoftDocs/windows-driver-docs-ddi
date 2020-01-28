---
UID: NC:video.PI2C_START
title: PI2C_START (video.h)
description: The I2CStart function starts I2C communication.
old-location: display\i2cstart.htm
tech.root: display
ms.assetid: 90f0a38d-f50e-4da0-b98f-2f3068f03b2e
ms.date: 05/10/2018
ms.keywords: I2CStart, I2CStart callback function [Display Devices], PI2C_START, PI2C_START callback, VideoPort_Functions_287e51cf-dce0-47c5-b743-c6fb401bb74e.xml, display.i2cstart, video/I2CStart
f1_keywords:
 - "video/I2CStart"
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
- I2CStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI2C_START callback function


## -description


The <i>I2CStart</i> function starts <a href="https://docs.microsoft.com/windows-hardware/drivers/">I2C</a> communication.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_i2c_callbacks">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


## -returns



<i>I2CStart</i> returns <b>TRUE</b> if I²C communication was successfully started, and <b>FALSE</b> otherwise.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a>
 

 

