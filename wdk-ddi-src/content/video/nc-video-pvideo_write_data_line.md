---
UID: NC:video.PVIDEO_WRITE_DATA_LINE
title: PVIDEO_WRITE_DATA_LINE
author: windows-driver-content
description: WriteDataLine sets the I2C serial data line to high or low.
old-location: display\writedataline.htm
old-project: display
ms.assetid: 3f860619-a479-4291-b3f3-ea4d309beee7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.writedataline, WriteDataLine callback function [Display Devices], WriteDataLine, PVIDEO_WRITE_DATA_LINE, PVIDEO_WRITE_DATA_LINE, video/WriteDataLine, VideoMiniport_Functions_35effeac-fbe1-44b9-905f-111460800d86.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	WriteDataLine
product: Windows
targetos: Windows
req.typenames: "*PVHF_CONFIG, VHF_CONFIG"
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

<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>



<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>



<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>



<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_WRITE_DATA_LINE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

