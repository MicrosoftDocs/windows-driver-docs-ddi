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
req.irql: See Remarks section.
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


The DDC_CONTROL structure holds function pointers and <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">EDID</a> segment information needed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a> function, which is exported by the video port driver. The <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function, implemented by the video miniport driver, can call <b>VideoPortDDCMonitorHelper</b> for assistance in reading the EDID blocks from its child monitor devices.


## -struct-fields




### -field Size

Specifies the size, in bytes, of this DDC_CONTROL structure.


### -field I2CCallbacks

Is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567382">I2C_CALLBACKS</a> structure that contains pointers to functions, implemented by the video miniport driver, that read and write individual data bits to the I2C serial clock and data lines.


### -field EdidSegment

Specifies the particular EDID segment. Currently, this member is meaningful only for EEDID (EDID Version 1.3); for other EDID versions, this member should always be set to 0. For EEDID (EDID Version 1.3), segment numbers can range from 0 through 127, where each segment is 256 bytes in length. Since the EDID version number is in segment 0, this member must be set to 0 the first time  the video miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a> regarding a particular monitor.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/1051a234-ef63-454e-8957-292e86f4efcd">ReadClockLine</a>



<a href="https://msdn.microsoft.com/071000a3-c1b7-47fd-aec7-9e9f32edddf6">ReadDataLine</a>



<a href="https://msdn.microsoft.com/4dfd6223-420e-4087-b5bd-8277575321f7">WriteClockLine</a>



<a href="https://msdn.microsoft.com/3f860619-a479-4291-b3f3-ea4d309beee7">WriteDataLine</a>
 

 

