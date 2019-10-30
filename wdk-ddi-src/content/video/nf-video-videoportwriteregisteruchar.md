---
UID: NF:video.VideoPortWriteRegisterUchar
title: VideoPortWriteRegisterUchar function (video.h)
description: The VideoPortWriteRegisterUchar function writes a byte to a mapped register.
old-location: display\videoportwriteregisteruchar.htm
tech.root: display
ms.assetid: 259d01a5-d975-48f9-b0cf-4596d12046bc
ms.date: 05/10/2018
ms.keywords: VideoPortWriteRegisterUchar, VideoPortWriteRegisterUchar function [Display Devices], VideoPort_Functions_b06fef25-2c8e-457f-9f6a-0f58573ac860.xml, display.videoportwriteregisteruchar, video/VideoPortWriteRegisterUchar
ms.topic: function
f1_keywords:
 - "video/VideoPortWriteRegisterUchar"
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
- VideoPortWriteRegisterUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterUchar function


## -description


The <b>VideoPortWriteRegisterUchar</b> function writes a byte to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a byte to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUchar</b>.

Callers of <b>VideoPortWriteRegisterUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

