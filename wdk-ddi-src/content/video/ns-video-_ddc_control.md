---
UID: NS:video._DDC_CONTROL
title: "_DDC_CONTROL"
author: windows-driver-content
description: The DDC_CONTROL structure holds function pointers and EDID segment information needed by the VideoPortDDCMonitorHelper function, which is exported by the video port driver.
old-location: display\ddc_control.htm
old-project: display
ms.assetid: 993c4913-1613-4ffb-86dd-fd8846139a46
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DDC_CONTROL, video/PDDC_CONTROL, PDDC_CONTROL, *PDDC_CONTROL, Video_Structs_d3006e08-ed2e-471d-b9c1-326a35aaf8bf.xml, DDC_CONTROL structure [Display Devices], video/DDC_CONTROL, PDDC_CONTROL structure pointer [Display Devices], display.ddc_control, _DDC_CONTROL
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
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

<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>



<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>



<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDC_CONTROL structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

