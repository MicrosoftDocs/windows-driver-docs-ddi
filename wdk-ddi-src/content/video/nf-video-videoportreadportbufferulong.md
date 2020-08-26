---
UID: NF:video.VideoPortReadPortBufferUlong
title: VideoPortReadPortBufferUlong function (video.h)
description: The VideoPortReadPortBufferUlong function reads a number of ULONG values from a mapped I/O port and writes them into a buffer.
old-location: display\videoportreadportbufferulong.htm
tech.root: display
ms.assetid: ecc09ca7-77fe-434f-9892-c2ae93d7d73c
ms.date: 05/10/2018
keywords: ["VideoPortReadPortBufferUlong function"]
ms.keywords: VideoPortReadPortBufferUlong, VideoPortReadPortBufferUlong function [Display Devices], VideoPort_Functions_a73970c1-c2cd-4d3c-a6e3-194eaacb978a.xml, display.videoportreadportbufferulong, video/VideoPortReadPortBufferUlong
f1_keywords:
 - "video/VideoPortReadPortBufferUlong"
 - "VideoPortReadPortBufferUlong"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortReadPortBufferUlong
targetos: Windows
req.typenames: 
---

# VideoPortReadPortBufferUlong function


## -description


The <b>VideoPortReadPortBufferUlong</b> function reads a number of ULONG values from a mapped I/O port and writes them into a buffer.


## -parameters




### -param Port

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Buffer 
[out]
Pointer to a buffer into which the ULONG values are written.


### -param Count

Specifies the number of ULONG values to be written to the buffer.


## -returns



None




## -remarks



The buffer must be large enough to contain at least the specified number of ULONG values.

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortBufferUlong</b>.

Callers of <b>VideoPortReadPortBufferUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

