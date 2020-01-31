---
UID: NC:video.PVIDEO_WRITE_DATA_LINE
title: PVIDEO_WRITE_DATA_LINE (video.h)
description: WriteDataLine sets the I2C serial data line to high or low.
old-location: display\writedataline.htm
tech.root: display
ms.assetid: 3f860619-a479-4291-b3f3-ea4d309beee7
ms.date: 05/10/2018
ms.keywords: PVIDEO_WRITE_DATA_LINE, PVIDEO_WRITE_DATA_LINE callback, VideoMiniport_Functions_35effeac-fbe1-44b9-905f-111460800d86.xml, WriteDataLine, WriteDataLine callback function [Display Devices], display.writedataline, video/WriteDataLine
f1_keywords:
 - "video/WriteDataLine"
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
- WriteDataLine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_WRITE_DATA_LINE callback function


## -description


<i>WriteDataLine</i> sets the I2C serial data line to high or low.


## -parameters




### -param HwDeviceExtension

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.


### -param Data

Supplies a value that specifies whether to set the serial data line to high or low. A value of 0 specifies that the data line should be set to low, and a value of 1 specifies that the data line should be set to high.


## -remarks



<i>WriteDataLine</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_data_line">ReadDataLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>
 

 

