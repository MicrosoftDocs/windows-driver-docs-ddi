---
UID: NF:video.VideoPortReadRegisterUlong
title: VideoPortReadRegisterUlong function (video.h)
description: The VideoPortReadRegisterUlong function reads a ULONG value from a mapped register range.
old-location: display\videoportreadregisterulong.htm
tech.root: display
ms.assetid: f63f6f55-ceec-4105-9002-f81874e0ac49
ms.date: 05/10/2018
ms.keywords: VideoPortReadRegisterUlong, VideoPortReadRegisterUlong function [Display Devices], VideoPort_Functions_d9150c11-0135-48c2-920e-9d5bcbbdd416.xml, display.videoportreadregisterulong, video/VideoPortReadRegisterUlong
ms.topic: function
f1_keywords:
 - "video/VideoPortReadRegisterUlong"
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
- VideoPortReadRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadRegisterUlong function


## -description


The <b>VideoPortReadRegisterUlong</b> function reads a ULONG value from a mapped register range.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadRegisterUlong</b> returns the ULONG value read from the adapter.




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterUlong</b>.

Callers of <b>VideoPortReadRegisterUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

