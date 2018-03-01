---
UID: NF:video.VideoPortReadRegisterUshort
title: VideoPortReadRegisterUshort function
author: windows-driver-content
description: The VideoPortReadRegisterUshort function reads a USHORT value from a mapped register range.
old-location: display\videoportreadregisterushort.htm
old-project: display
ms.assetid: fdf5d153-74ca-437e-82ab-b85c89dc9fd1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReadRegisterUshort, VideoPortReadRegisterUshort function [Display Devices], VideoPort_Functions_c6ee8be3-3b15-4f22-8008-63d132ec7379.xml, display.videoportreadregisterushort, video/VideoPortReadRegisterUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReadRegisterUshort function


## -description


The <b>VideoPortReadRegisterUshort</b> function reads a USHORT value from a mapped register range.


## -syntax


````
USHORT VideoPortReadRegisterUshort(
   PUSHORT Register
);
````


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadRegisterUshort</b> returns the USHORT value read from the adapter.




## -remarks



A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterUshort</b>.

Callers of <b>VideoPortReadRegisterUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReadRegisterUshort function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

