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
-	ReadDataLine
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

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns



<i>ReadDataLine</i> returns 1 if the serial data line is high and 0 if the serial data line is low.




## -remarks



<i>ReadDataLine</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/1051a234-ef63-454e-8957-292e86f4efcd">ReadClockLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/4dfd6223-420e-4087-b5bd-8277575321f7">WriteClockLine</a>



<a href="https://msdn.microsoft.com/3f860619-a479-4291-b3f3-ea4d309beee7">WriteDataLine</a>
 

 

