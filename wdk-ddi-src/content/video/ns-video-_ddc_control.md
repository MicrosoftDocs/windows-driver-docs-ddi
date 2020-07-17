---
UID: NS:video._DDC_CONTROL
title: _DDC_CONTROL (video.h)
description: The DDC_CONTROL structure holds function pointers and EDID segment information needed by the VideoPortDDCMonitorHelper function, which is exported by the video port driver.
old-location: display\ddc_control.htm
tech.root: display
ms.assetid: 993c4913-1613-4ffb-86dd-fd8846139a46
ms.date: 05/10/2018
keywords: ["_DDC_CONTROL structure"]
ms.keywords: "*PDDC_CONTROL, DDC_CONTROL, DDC_CONTROL structure [Display Devices], PDDC_CONTROL, PDDC_CONTROL structure pointer [Display Devices], Video_Structs_d3006e08-ed2e-471d-b9c1-326a35aaf8bf.xml, _DDC_CONTROL, display.ddc_control, video/DDC_CONTROL, video/PDDC_CONTROL"
f1_keywords:
 - "video/DDC_CONTROL"
 - "DDC_CONTROL"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- DDC_CONTROL
product:
- Windows
targetos: Windows
req.typenames: DDC_CONTROL, *PDDC_CONTROL
---

# _DDC_CONTROL structure


## -description


The DDC_CONTROL structure holds function pointers and <a href="https://docs.microsoft.com/windows-hardware/drivers/">EDID</a> segment information needed by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a> function, which is exported by the video port driver. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a> function, implemented by the video miniport driver, can call <b>VideoPortDDCMonitorHelper</b> for assistance in reading the EDID blocks from its child monitor devices.


## -struct-fields




### -field Size

Specifies the size, in bytes, of this DDC_CONTROL structure.


### -field I2CCallbacks

Is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_i2c_callbacks">I2C_CALLBACKS</a> structure that contains pointers to functions, implemented by the video miniport driver, that read and write individual data bits to the I2C serial clock and data lines.


### -field EdidSegment

Specifies the particular EDID segment. Currently, this member is meaningful only for EEDID (EDID Version 1.3); for other EDID versions, this member should always be set to 0. For EEDID (EDID Version 1.3), segment numbers can range from 0 through 127, where each segment is 256 bytes in length. Since the EDID version number is in segment 0, this member must be set to 0 the first time  the video miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a> regarding a particular monitor.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I2C Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_clock_line">ReadClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_read_data_line">ReadDataLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_clock_line">WriteClockLine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_write_data_line">WriteDataLine</a>
 

 

