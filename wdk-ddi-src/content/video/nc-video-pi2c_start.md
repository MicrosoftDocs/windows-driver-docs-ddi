---
UID: NC:video.PI2C_START
title: PI2C_START
author: windows-driver-content
description: The I2CStart function starts I2C communication.
old-location: display\i2cstart.htm
old-project: display
ms.assetid: 90f0a38d-f50e-4da0-b98f-2f3068f03b2e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: I2CStart, I2CStart callback function [Display Devices], PI2C_START, VideoPort_Functions_287e51cf-dce0-47c5-b743-c6fb401bb74e.xml, display.i2cstart, video/I2CStart
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
-	I2CStart
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PI2C_START callback


## -description


The <i>I2CStart</i> function starts <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> communication.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter device extension.


### -param I2CCallbacks [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567382">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.


## -returns



<i>I2CStart</i> returns <b>TRUE</b> if I²C communication was successfully started, and <b>FALSE</b> otherwise.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a>
 

 

