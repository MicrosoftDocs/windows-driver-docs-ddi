---
UID: NC:video.PI2C_READ
title: PI2C_READ
description: The I2CRead function reads data over the I2C channel.
old-location: display\i2cread.htm
tech.root: display
ms.assetid: 1418ec29-be67-46af-b6db-0b534ecafb37
ms.date: 05/10/2018
ms.keywords: I2CRead, I2CRead callback function [Display Devices], PI2C_READ, PI2C_READ callback, VideoPort_Functions_cb73b3b1-1646-43ef-ac61-5a14c9a53b9b.xml, display.i2cread, video/I2CRead
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
-	I2CRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# PI2C_READ callback function


## -description


The <i>I2CRead</i> function reads data over the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> channel.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567382">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


### -param Buffer [out]

Pointer to the data to be read.


### -param Length [in]

Specifies the number of bytes to be read.


## -returns



<i>I2CRead</i> returns <b>TRUE</b> if the data was successfully read, and <b>FALSE</b> otherwise.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a>
 

 

