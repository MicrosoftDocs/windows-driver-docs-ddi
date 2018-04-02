---
UID: NC:video.PI2C_WRITE
title: PI2C_WRITE
author: windows-driver-content
description: The I2CWrite function writes data over the I2C channel.
old-location: display\i2cwrite.htm
old-project: display
ms.assetid: 5aaebf38-bc09-4fb5-969e-7b456773d5ac
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: I2CWrite, I2CWrite callback function [Display Devices], PI2C_WRITE, VideoPort_Functions_3e35f4d8-7c13-4c2c-b0e4-c518bc63e6f6.xml, display.i2cwrite, video/I2CWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	I2CWrite
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PI2C_WRITE callback


## -description


The <i>I2CWrite</i> function writes data over the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> channel.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567382">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


### -param Buffer [in]

Pointer to the data to be written.


### -param Length [in]

Specifies the number of bytes to be written.


## -returns



<i>I2CWrite</i> returns <b>TRUE</b> if the data was successfully written, and <b>FALSE</b> otherwise.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a>
 

 

