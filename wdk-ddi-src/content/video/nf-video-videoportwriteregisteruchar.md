---
UID: NF:video.VideoPortWriteRegisterUchar
title: VideoPortWriteRegisterUchar function
author: windows-driver-content
description: The VideoPortWriteRegisterUchar function writes a byte to a mapped register.
old-location: display\videoportwriteregisteruchar.htm
old-project: display
ms.assetid: 259d01a5-d975-48f9-b0cf-4596d12046bc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportwriteregisteruchar, VideoPort_Functions_b06fef25-2c8e-457f-9f6a-0f58573ac860.xml, VideoPortWriteRegisterUchar function [Display Devices], video/VideoPortWriteRegisterUchar, VideoPortWriteRegisterUchar
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortWriteRegisterUchar
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
---

# VideoPortWriteRegisterUchar function


## -description


The <b>VideoPortWriteRegisterUchar</b> function writes a byte to a mapped register.


## -syntax


````
VOID VideoPortWriteRegisterUchar(
   PUCHAR Register,
   UCHAR  Value
);
````


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a byte to be transferred to the adapter.


## -returns


None



## -remarks


A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUchar</b>.

Callers of <b>VideoPortWriteRegisterUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.



## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortWriteRegisterUchar function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

