---
UID: NC:video.PVIDEO_READ_CLOCK_LINE
title: PVIDEO_READ_CLOCK_LINE
author: windows-driver-content
description: ReadClockLine reads a single data bit from the I2C serial clock line.
old-location: display\readclockline.htm
tech.root: display
ms.assetid: 1051a234-ef63-454e-8957-292e86f4efcd
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PVIDEO_READ_CLOCK_LINE, PVIDEO_READ_CLOCK_LINE callback, ReadClockLine, ReadClockLine callback function [Display Devices], VideoMiniport_Functions_5e7bcadb-43ea-4a1b-81b7-666cabd66aa0.xml, display.readclockline, video/ReadClockLine
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
-	ReadClockLine
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

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns



<i>ReadClockLine</i> returns 1 if the serial clock line is high and 0 if the serial clock line is low.




## -remarks



<i>ReadClockLine</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/071000a3-c1b7-47fd-aec7-9e9f32edddf6">ReadDataLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/4dfd6223-420e-4087-b5bd-8277575321f7">WriteClockLine</a>



<a href="https://msdn.microsoft.com/3f860619-a479-4291-b3f3-ea4d309beee7">WriteDataLine</a>
 

 

