---
UID: NS:video._I2C_CALLBACKS
title: "_I2C_CALLBACKS"
author: windows-driver-content
description: The I2C_CALLBACKS structure contains pointers to functions, implemented by the video miniport driver, that read from and write to the serial data and serial clock lines of the I2C bus.
old-location: display\i2c_callbacks.htm
old-project: display
ms.assetid: fc67ef79-41c8-414c-aaa9-ef8a80edd696
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PI2C_CALLBACKS, I2C_CALLBACKS, I2C_CALLBACKS structure [Display Devices], PI2C_CALLBACKS, PI2C_CALLBACKS structure pointer [Display Devices], Video_Structs_fc21393a-6df2-4b4f-89be-2d3ac46dfcd7.xml, _I2C_CALLBACKS, display.i2c_callbacks, video/I2C_CALLBACKS, video/PI2C_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	I2C_CALLBACKS
product: Windows
targetos: Windows
req.typenames: I2C_CALLBACKS, *PI2C_CALLBACKS
req.product: Windows 10 or later.
---

# _I2C_CALLBACKS structure


## -description


The I2C_CALLBACKS structure contains pointers to functions, implemented by the video miniport driver, that read from and write to the serial data and serial clock lines of the I2C bus.


## -struct-fields




### -field WriteClockLine

A pointer to the <a href="https://msdn.microsoft.com/4dfd6223-420e-4087-b5bd-8277575321f7">WriteClockLine</a> function implemented by the video miniport driver.


### -field WriteDataLine

A pointer to the <a href="https://msdn.microsoft.com/3f860619-a479-4291-b3f3-ea4d309beee7">WriteDataLine</a> function implemented by the video miniport driver.


### -field ReadClockLine

A pointer to the <a href="https://msdn.microsoft.com/1051a234-ef63-454e-8957-292e86f4efcd">ReadClockLine</a> function implemented by the video miniport driver.


### -field ReadDataLine

A pointer to the <a href="https://msdn.microsoft.com/071000a3-c1b7-47fd-aec7-9e9f32edddf6">ReadDataLine</a> function implemented by the video miniport driver.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549272">DDC_CONTROL</a>



<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>
 

 

