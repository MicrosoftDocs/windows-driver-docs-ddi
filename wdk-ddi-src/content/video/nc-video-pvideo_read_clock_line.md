---
UID: NC:video.PVIDEO_READ_CLOCK_LINE
title: PVIDEO_READ_CLOCK_LINE
author: windows-driver-content
description: ReadClockLine reads a single data bit from the I2C serial clock line.
old-location: display\readclockline.htm
old-project: display
ms.assetid: 1051a234-ef63-454e-8957-292e86f4efcd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
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
req.alt-api: ReadClockLine
req.alt-loc: video.h
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
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_READ_CLOCK_LINE callback



## -description
<i>ReadClockLine</i> reads a single data bit from the I2C serial clock line.



## -prototype

````
PVIDEO_READ_CLOCK_LINE ReadClockLine;

BOOLEAN ReadClockLine(
   PVOID HwDeviceExtension
)
{ ... }
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns
<i>ReadClockLine</i> returns 1 if the serial clock line is high and 0 if the serial clock line is low.


## -remarks
<i>ReadClockLine</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_READ_CLOCK_LINE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

