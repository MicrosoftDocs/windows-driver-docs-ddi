---
UID: NC:video.PVIDEO_WRITE_CLOCK_LINE
title: PVIDEO_WRITE_CLOCK_LINE (video.h)
description: WriteClockLine sets the I2C serial clock line to high or low.
old-location: display\writeclockline.htm
tech.root: display
ms.assetid: 4dfd6223-420e-4087-b5bd-8277575321f7
ms.date: 05/10/2018
keywords: ["PVIDEO_WRITE_CLOCK_LINE callback function"]
ms.keywords: PVIDEO_WRITE_CLOCK_LINE, PVIDEO_WRITE_CLOCK_LINE callback, VideoMiniport_Functions_7d36df35-ac09-4a82-af0c-47a733617d9a.xml, WriteClockLine, WriteClockLine callback function [Display Devices], display.writeclockline, video/WriteClockLine
f1_keywords:
 - "video/WriteClockLine"
 - "WriteClockLine"
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
- WriteClockLine
targetos: Windows
req.typenames: 
---

# PVIDEO_WRITE_CLOCK_LINE callback function


## -description


<i>WriteClockLine</i> sets the I2C serial clock line to high or low.


## -parameters




### -param HwDeviceExtension

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


### -param Data

Supplies a value that specifies whether to set the serial clock line to high or low. A value of 0 specifies that the clock line should be set to low, and a value of 1 specifies that the clock line should be set to high.


## -remarks



<i>WriteClockLine</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_data_line">ReadDataLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_data_line">WriteDataLine</a>
 

 

