---
UID: NF:video.VideoPortWriteRegisterBufferUchar
title: VideoPortWriteRegisterBufferUchar function (video.h)
description: The VideoPortWriteRegisterBufferUchar function writes a number of unsigned bytes to a mapped register.
old-location: display\videoportwriteregisterbufferuchar.htm
tech.root: display
ms.assetid: 43ceb589-e90f-4090-88ed-ada813ac6a6f
ms.date: 05/10/2018
keywords: ["VideoPortWriteRegisterBufferUchar function"]
ms.keywords: VideoPortWriteRegisterBufferUchar, VideoPortWriteRegisterBufferUchar function [Display Devices], VideoPort_Functions_5a9ee1e8-744e-4141-993d-1a1710599431.xml, display.videoportwriteregisterbufferuchar, video/VideoPortWriteRegisterBufferUchar
f1_keywords:
 - "video/VideoPortWriteRegisterBufferUchar"
 - "VideoPortWriteRegisterBufferUchar"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortWriteRegisterBufferUchar
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterBufferUchar function


## -description


The <b>VideoPortWriteRegisterBufferUchar</b> function writes a number of unsigned bytes to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Buffer 
[in]
Pointer to a buffer containing the bytes to be written.


### -param Count

Specifies the number of bytes to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterBufferUchar</b>.

Callers of <b>VideoPortWriteRegisterBufferUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

