---
UID: NF:video.VideoPortWriteRegisterBufferUshort
title: VideoPortWriteRegisterBufferUshort function
author: windows-driver-content
description: The VideoPortWriteRegisterBufferUshort function writes a number of USHORT values to a mapped register.
old-location: display\videoportwriteregisterbufferushort.htm
old-project: display
ms.assetid: 52bc00d5-313c-444d-91d9-8f95640e7d81
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , B, P, R, U, V, VideoPortWriteRegisterBufferUshort, VideoPortWriteRegisterBufferUshort function [Display Devices], VideoPort_Functions_f385c5d4-bc63-4aae-b021-b503f6a5336f.xml, W, d, display.videoportwriteregisterbufferushort, e, f, g, h, i, o, r, s, t, u, video/VideoPortWriteRegisterBufferUshort"
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
-	VideoPortWriteRegisterBufferUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortWriteRegisterBufferUshort function


## -description


The <b>VideoPortWriteRegisterBufferUshort</b> function writes a number of USHORT values to a mapped register.


## -syntax


````
VOID VideoPortWriteRegisterBufferUshort(
       PUSHORT Register,
  _In_ PUSHORT Buffer,
       ULONG   Count
);
````


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


### -param Buffer [in]

Pointer to a buffer containing the USHORT values to be written.


### -param Count

Specifies the number of USHORT values to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterBufferUshort</b>.

Callers of <b>VideoPortWriteRegisterBufferUshort</b>can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortWriteRegisterBufferUshort function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

