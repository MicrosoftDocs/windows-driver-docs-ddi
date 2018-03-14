---
UID: NS:video._I2C_CALLBACKS
title: "_I2C_CALLBACKS"
author: windows-driver-content
description: The I2C_CALLBACKS structure contains pointers to functions, implemented by the video miniport driver, that read from and write to the serial data and serial clock lines of the I2C bus.
old-location: display\i2c_callbacks.htm
old-project: display
ms.assetid: fc67ef79-41c8-414c-aaa9-ef8a80edd696
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
req.irql: "<= DISPATCH_LEVEL"
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


## -syntax


````
typedef struct _I2C_CALLBACKS {
  PVIDEO_WRITE_CLOCK_LINE WriteClockLine;
  PVIDEO_WRITE_DATA_LINE  WriteDataLine;
  PVIDEO_READ_CLOCK_LINE  ReadClockLine;
  PVIDEO_READ_DATA_LINE   ReadDataLine;
} I2C_CALLBACKS, *PI2C_CALLBACKS;
````


## -struct-fields




### -field WriteClockLine

A pointer to the <a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a> function implemented by the video miniport driver.


### -field WriteDataLine

A pointer to the <a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a> function implemented by the video miniport driver.


### -field ReadClockLine

A pointer to the <a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a> function implemented by the video miniport driver.


### -field ReadDataLine

A pointer to the <a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a> function implemented by the video miniport driver.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\ns-video-_ddc_control.md">DDC_CONTROL</a>



<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>



<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>



 

 


