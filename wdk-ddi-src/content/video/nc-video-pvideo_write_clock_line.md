---
UID: NC:video.PVIDEO_WRITE_CLOCK_LINE
title: PVIDEO_WRITE_CLOCK_LINE
author: windows-driver-content
description: WriteClockLine sets the I2C serial clock line to high or low.
old-location: display\writeclockline.htm
tech.root: display
ms.assetid: 4dfd6223-420e-4087-b5bd-8277575321f7
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PVIDEO_WRITE_CLOCK_LINE, PVIDEO_WRITE_CLOCK_LINE callback, VideoMiniport_Functions_7d36df35-ac09-4a82-af0c-47a733617d9a.xml, WriteClockLine, WriteClockLine callback function [Display Devices], display.writeclockline, video/WriteClockLine
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
-	WriteClockLine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_WRITE_CLOCK_LINE callback function


## -description


<i>WriteClockLine</i> sets the I2C serial clock line to high or low.


## -parameters




### -param HwDeviceExtension

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Data

Supplies a value that specifies whether to set the serial clock line to high or low. A value of 0 specifies that the clock line should be set to low, and a value of 1 specifies that the clock line should be set to high.


## -returns



None




## -remarks



<i>WriteClockLine</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/1051a234-ef63-454e-8957-292e86f4efcd">ReadClockLine</a>



<a href="https://msdn.microsoft.com/071000a3-c1b7-47fd-aec7-9e9f32edddf6">ReadDataLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/3f860619-a479-4291-b3f3-ea4d309beee7">WriteDataLine</a>
 

 

