---
UID: NC:video.PVIDEO_READ_DATA_LINE
title: PVIDEO_READ_DATA_LINE (video.h)
description: ReadDataLine reads a single data bit from the I2C serial data line.
old-location: display\readdataline.htm
tech.root: display
ms.assetid: 071000a3-c1b7-47fd-aec7-9e9f32edddf6
ms.date: 05/10/2018
ms.keywords: PVIDEO_READ_DATA_LINE, PVIDEO_READ_DATA_LINE callback, ReadDataLine, ReadDataLine callback function [Display Devices], VideoMiniport_Functions_6507a035-50bc-4a1e-92bf-f07e75cf023b.xml, display.readdataline, video/ReadDataLine
ms.topic: callback
f1_keywords:
 - "video/ReadDataLine"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
- UserDefined
api_location:
- video.h
api_name:
- ReadDataLine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_READ_DATA_LINE callback function


## -description


<i>ReadDataLine</i> reads a single data bit from the I2C serial data line.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


## -returns



<i>ReadDataLine</i> returns 1 if the serial data line is high and 0 if the serial data line is low.




## -remarks



<i>ReadDataLine</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_data_line">WriteDataLine</a>
 

 

