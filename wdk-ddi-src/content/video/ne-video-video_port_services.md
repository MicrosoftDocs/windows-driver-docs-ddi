---
UID: NE:video.VIDEO_PORT_SERVICES
title: VIDEO_PORT_SERVICES
author: windows-driver-content
description: The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling VideoPortQueryServices.
old-location: display\video_port_services.htm
old-project: display
ms.assetid: 3ca53536-e847-4c11-a28d-e046e8a392de
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: video/VideoPortServicesWCMemoryProtection, VIDEO_PORT_SERVICES enumeration [Display Devices], VideoPortServicesDebugReport, video/VIDEO_PORT_SERVICES, video/VideoPortServicesDebugReport, VideoPortServicesInt10, video/VideoPortServicesI2C, video/VideoPortServicesInt10, VideoPortServicesWCMemoryProtection, VIDEO_PORT_SERVICES, display.video_port_services, VideoPortServicesHeadless, VideoPortServicesI2C, video/VideoPortServicesHeadless, Video_Structs_f2ede654-971a-4700-a911-8063a2a03ffe.xml, video/VideoPortServicesAGP, VideoPortServicesAGP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VIDEO_PORT_SERVICES
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VIDEO_PORT_SERVICES enumeration


## -description


The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>.


## -syntax


````
typedef enum  { 
  VideoPortServicesAGP                 = 1,
  VideoPortServicesI2C,
  VideoPortServicesHeadless,
  VideoPortServicesInt10,
  VideoPortServicesDebugReport,
  VideoPortServicesWCMemoryProtection
} VIDEO_PORT_SERVICES;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567384">I2C Functions Implemented by the Video Port Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538227">AGP Functions Implemented by the Video Port Driver</a>



<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551792">Debug Report Functions Implemented by the Video Port Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567384">I2C Functions Implemented by the Video Port Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_SERVICES enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

