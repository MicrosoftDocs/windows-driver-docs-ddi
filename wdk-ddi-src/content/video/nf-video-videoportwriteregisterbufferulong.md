---
UID: NF:video.VideoPortWriteRegisterBufferUlong
title: VideoPortWriteRegisterBufferUlong function (video.h)
description: The VideoPortWriteRegisterBufferUlong function writes a number of ULONG values to a mapped register.
old-location: display\videoportwriteregisterbufferulong.htm
tech.root: display
ms.assetid: 48322143-8c95-4ffa-ac7a-597ed5fb066c
ms.date: 05/10/2018
keywords: ["VideoPortWriteRegisterBufferUlong function"]
ms.keywords: VideoPortWriteRegisterBufferUlong, VideoPortWriteRegisterBufferUlong function [Display Devices], VideoPort_Functions_c9709e69-cf6e-4772-8889-0c37f79c0b22.xml, display.videoportwriteregisterbufferulong, video/VideoPortWriteRegisterBufferUlong
f1_keywords:
 - "video/VideoPortWriteRegisterBufferUlong"
 - "VideoPortWriteRegisterBufferUlong"
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
- VideoPortWriteRegisterBufferUlong
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterBufferUlong function


## -description


The <b>VideoPortWriteRegisterBufferUlong</b> function writes a number of ULONG values to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Buffer [in]

Pointer to a buffer containing the ULONG values to be written.


### -param Count

Specifies the number of ULONG values to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterBufferUlong</b>.

Callers of <b>VideoPortWriteRegisterBufferUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

