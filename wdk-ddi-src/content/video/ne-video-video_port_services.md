---
UID: NE:video.__unnamed_enum_2
title: VIDEO_PORT_SERVICES (video.h)
description: The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling VideoPortQueryServices.
old-location: display\video_port_services.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VIDEO_PORT_SERVICES enumeration"]
ms.keywords: VIDEO_PORT_SERVICES, VIDEO_PORT_SERVICES enumeration [Display Devices], VideoPortServicesAGP, VideoPortServicesDebugReport, VideoPortServicesHeadless, VideoPortServicesI2C, VideoPortServicesInt10, VideoPortServicesWCMemoryProtection, Video_Structs_f2ede654-971a-4700-a911-8063a2a03ffe.xml, display.video_port_services, video/VIDEO_PORT_SERVICES, video/VideoPortServicesAGP, video/VideoPortServicesDebugReport, video/VideoPortServicesHeadless, video/VideoPortServicesI2C, video/VideoPortServicesInt10, video/VideoPortServicesWCMemoryProtection
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
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
f1_keywords:
 - VIDEO_PORT_SERVICES
 - video/VIDEO_PORT_SERVICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - video.h
api_name:
 - VIDEO_PORT_SERVICES
---

# VIDEO_PORT_SERVICES enumeration


## -description

The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>.

## -enum-fields

### -field VideoPortServicesAGP

Represents the AGP interface.

### -field VideoPortServicesI2C

Represents the I2C interface.

### -field VideoPortServicesHeadless

Represents the Headless interface.

### -field VideoPortServicesInt10

Represents the Int10 interface.

### -field VideoPortServicesDebugReport

Represents the Debug Report interface, which is available in the following operating systems:
 


<ul>
<li>Windows Server 2003 SP1 and subsequent service packs</li>
<li>Windows XP SP2 and subsequent service packs </li>
</ul>

### -field VideoPortServicesWCMemoryProtection

Represents the WC Memory Protection interface.

## -remarks

Many functions are exported by the video port driver; the video miniport driver can call those functions using ordinary dynamic linking. Other functions implemented by the video port driver are not exported; instead, they are made available to the video miniport driver through function pointers. An interface, in this context, is a set of related function pointers. For example, the AGP interface is a set of pointers to functions (implemented by the video port driver) that provide AGP services to the video miniport driver.

The video miniport driver obtains a set of function pointers by passing a value from the VIDEO_PORT_SERVICES enumerated type to the <i>ServicesType</i> parameter of the <b>VideoPortQueryServices</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/videoagp/">AGP Functions Implemented by the Video Port Driver</a>



<a href="/windows-hardware/drivers/ddi/index">Debug Report Functions Implemented by the Video Port Driver</a>



<a href="/windows-hardware/drivers/ddi/index">I2C Functions Implemented by the Video Port Driver</a>



<a href="/windows-hardware/drivers/ddi/index">Int10 Functions Implemented by the Video Port Driver</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
