---
UID: NC:video.PVIDEO_READ_CLOCK_LINE
title: PVIDEO_READ_CLOCK_LINE (video.h)
description: ReadClockLine reads a single data bit from the I2C serial clock line.
old-location: display\readclockline.htm
tech.root: display
ms.assetid: 1051a234-ef63-454e-8957-292e86f4efcd
ms.date: 05/10/2018
ms.keywords: PVIDEO_READ_CLOCK_LINE, PVIDEO_READ_CLOCK_LINE callback, ReadClockLine, ReadClockLine callback function [Display Devices], VideoMiniport_Functions_5e7bcadb-43ea-4a1b-81b7-666cabd66aa0.xml, display.readclockline, video/ReadClockLine
ms.topic: callback
f1_keywords:
 - "video/ReadClockLine"
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
- ReadClockLine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_READ_CLOCK_LINE callback function


## -description


<i>ReadClockLine</i> reads a single data bit from the I2C serial clock line.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


## -returns



<i>ReadClockLine</i> returns 1 if the serial clock line is high and 0 if the serial clock line is low.




## -remarks



<i>ReadClockLine</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_data_line">ReadDataLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_data_line">WriteDataLine</a>
 

 

