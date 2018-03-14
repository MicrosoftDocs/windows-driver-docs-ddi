---
UID: NS:video._DDC_CONTROL
title: "_DDC_CONTROL"
author: windows-driver-content
description: The DDC_CONTROL structure holds function pointers and EDID segment information needed by the VideoPortDDCMonitorHelper function, which is exported by the video port driver.
old-location: display\ddc_control.htm
old-project: display
ms.assetid: 993c4913-1613-4ffb-86dd-fd8846139a46
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDDC_CONTROL, DDC_CONTROL, DDC_CONTROL structure [Display Devices], PDDC_CONTROL, PDDC_CONTROL structure pointer [Display Devices], Video_Structs_d3006e08-ed2e-471d-b9c1-326a35aaf8bf.xml, _DDC_CONTROL, display.ddc_control, video/DDC_CONTROL, video/PDDC_CONTROL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	DDC_CONTROL
product: Windows
targetos: Windows
req.typenames: DDC_CONTROL, *PDDC_CONTROL
req.product: Windows 10 or later.
---

# _DDC_CONTROL structure


## -description


The DDC_CONTROL structure holds function pointers and <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">EDID</a> segment information needed by the <a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a> function, which is exported by the video port driver. The <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> function, implemented by the video miniport driver, can call <b>VideoPortDDCMonitorHelper</b> for assistance in reading the EDID blocks from its child monitor devices.


## -syntax


````
typedef struct _DDC_CONTROL {
  ULONG         Size;
  I2C_CALLBACKS I2CCallbacks;
  UCHAR         EdidSegment;
} DDC_CONTROL, *PDDC_CONTROL;
````


## -struct-fields




### -field Size

Specifies the size, in bytes, of this DDC_CONTROL structure.


### -field I2CCallbacks

Is an <a href="..\video\ns-video-_i2c_callbacks.md">I2C_CALLBACKS</a> structure that contains pointers to functions, implemented by the video miniport driver, that read and write individual data bits to the I2C serial clock and data lines.


### -field EdidSegment

Specifies the particular EDID segment. Currently, this member is meaningful only for EEDID (EDID Version 1.3); for other EDID versions, this member should always be set to 0. For EEDID (EDID Version 1.3), segment numbers can range from 0 through 127, where each segment is 256 bytes in length. Since the EDID version number is in segment 0, this member must be set to 0 the first time  the video miniport driver calls <a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a> regarding a particular monitor.


## -see-also

<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>



<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>



<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>



 

 


