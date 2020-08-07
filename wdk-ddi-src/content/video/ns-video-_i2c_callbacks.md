---
UID: NS:video._I2C_CALLBACKS
title: _I2C_CALLBACKS (video.h)
description: The I2C_CALLBACKS structure contains pointers to functions, implemented by the video miniport driver, that read from and write to the serial data and serial clock lines of the I2C bus.
old-location: display\i2c_callbacks.htm
tech.root: display
ms.assetid: fc67ef79-41c8-414c-aaa9-ef8a80edd696
ms.date: 05/10/2018
keywords: ["I2C_CALLBACKS structure"]
ms.keywords: "*PI2C_CALLBACKS, I2C_CALLBACKS, I2C_CALLBACKS structure [Display Devices], PI2C_CALLBACKS, PI2C_CALLBACKS structure pointer [Display Devices], Video_Structs_fc21393a-6df2-4b4f-89be-2d3ac46dfcd7.xml, _I2C_CALLBACKS, display.i2c_callbacks, video/I2C_CALLBACKS, video/PI2C_CALLBACKS"
f1_keywords:
 - "video/I2C_CALLBACKS"
 - "I2C_CALLBACKS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- I2C_CALLBACKS
targetos: Windows
req.typenames: I2C_CALLBACKS, *PI2C_CALLBACKS
---

# _I2C_CALLBACKS structure


## -description


The I2C_CALLBACKS structure contains pointers to functions, implemented by the video miniport driver, that read from and write to the serial data and serial clock lines of the I2C bus.


## -struct-fields




### -field WriteClockLine

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_clock_line">WriteClockLine</a> function implemented by the video miniport driver.


### -field WriteDataLine

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_data_line">WriteDataLine</a> function implemented by the video miniport driver.


### -field ReadClockLine

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_clock_line">ReadClockLine</a> function implemented by the video miniport driver.


### -field ReadDataLine

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_data_line">ReadDataLine</a> function implemented by the video miniport driver.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_ddc_control">DDC_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>
 

 

