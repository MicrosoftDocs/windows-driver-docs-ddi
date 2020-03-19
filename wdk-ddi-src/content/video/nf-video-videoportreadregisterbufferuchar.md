---
UID: NF:video.VideoPortReadRegisterBufferUchar
title: VideoPortReadRegisterBufferUchar function (video.h)
description: The VideoPortReadRegisterBufferUchar function reads a number of bytes from a mapped device memory range and writes them into a buffer.
old-location: display\videoportreadregisterbufferuchar.htm
tech.root: display
ms.assetid: 2058374a-b74d-49e2-9c42-5972b11af677
ms.date: 05/10/2018
keywords: ["VideoPortReadRegisterBufferUchar function"]
ms.keywords: VideoPortReadRegisterBufferUchar, VideoPortReadRegisterBufferUchar function [Display Devices], VideoPort_Functions_9b0878ff-64ba-4d19-81aa-c5932ffa1953.xml, display.videoportreadregisterbufferuchar, video/VideoPortReadRegisterBufferUchar
f1_keywords:
 - "video/VideoPortReadRegisterBufferUchar"
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
- VideoPortReadRegisterBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadRegisterBufferUchar function


## -description


The <b>VideoPortReadRegisterBufferUchar</b> function reads a number of bytes from a mapped device memory range and writes them into a buffer.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Buffer [out]

Pointer to a buffer into which the UCHAR values are written.


### -param Count

Specifies the number of bytes to be written to the buffer.


## -returns



None




## -remarks



The buffer must be large enough to contain at least the specified number of bytes.

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterBufferUchar</b>.

Callers of <b>VideoPortReadRegisterBufferUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

