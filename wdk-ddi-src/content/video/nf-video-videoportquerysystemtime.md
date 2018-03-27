---
UID: NF:video.VideoPortQuerySystemTime
title: VideoPortQuerySystemTime function
author: windows-driver-content
description: The VideoPortQuerySystemTime function obtains the current system time.
old-location: display\videoportquerysystemtime.htm
old-project: display
ms.assetid: d9b54710-6ad2-4959-9172-76c90468d343
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortQuerySystemTime, VideoPortQuerySystemTime function [Display Devices], VideoPort_Functions_18c4e015-b294-40e0-8aef-7642d3a9cb27.xml, display.videoportquerysystemtime, video/VideoPortQuerySystemTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortQuerySystemTime
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortQuerySystemTime function


## -description


The <b>VideoPortQuerySystemTime</b> function obtains the current system time.


## -parameters




### -param CurrentTime [out]

Pointer to a memory location that will receive the current system time.


## -returns



None




## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570336">VideoPortQueryPerformanceCounter</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortQuerySystemTime function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

