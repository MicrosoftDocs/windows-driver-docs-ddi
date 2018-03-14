---
UID: NC:video.PVIDEO_WRITE_DATA_LINE
title: PVIDEO_WRITE_DATA_LINE
author: windows-driver-content
description: WriteDataLine sets the I2C serial data line to high or low.
old-location: display\writedataline.htm
old-project: display
ms.assetid: 3f860619-a479-4291-b3f3-ea4d309beee7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PVIDEO_WRITE_DATA_LINE, VideoMiniport_Functions_35effeac-fbe1-44b9-905f-111460800d86.xml, WriteDataLine, WriteDataLine callback function [Display Devices], display.writedataline, video/WriteDataLine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	WriteDataLine
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_WRITE_DATA_LINE callback


## -description


<i>WriteDataLine</i> sets the I2C serial data line to high or low.


## -prototype


````
PVIDEO_WRITE_DATA_LINE WriteDataLine;

VOID WriteDataLine(
   PVOID HwDeviceExtension,
   UCHAR Data
)
{ ... }
````


## -parameters




### -param HwDeviceExtension

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Data

Supplies a value that specifies whether to set the serial data line to high or low. A value of 0 specifies that the data line should be set to low, and a value of 1 specifies that the data line should be set to high.


## -returns



None




## -remarks



<i>WriteDataLine</i> should be made pageable.




## -see-also

<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>



<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>



<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>



 

 


