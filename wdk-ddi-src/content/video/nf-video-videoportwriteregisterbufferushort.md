---
UID: NF:video.VideoPortWriteRegisterBufferUshort
title: VideoPortWriteRegisterBufferUshort function (video.h)
description: The VideoPortWriteRegisterBufferUshort function writes a number of USHORT values to a mapped register.
old-location: display\videoportwriteregisterbufferushort.htm
tech.root: display
ms.assetid: 52bc00d5-313c-444d-91d9-8f95640e7d81
ms.date: 05/10/2018
keywords: ["VideoPortWriteRegisterBufferUshort function"]
ms.keywords: VideoPortWriteRegisterBufferUshort, VideoPortWriteRegisterBufferUshort function [Display Devices], VideoPort_Functions_f385c5d4-bc63-4aae-b021-b503f6a5336f.xml, display.videoportwriteregisterbufferushort, video/VideoPortWriteRegisterBufferUshort
f1_keywords:
 - "video/VideoPortWriteRegisterBufferUshort"
 - "VideoPortWriteRegisterBufferUshort"
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
- VideoPortWriteRegisterBufferUshort
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterBufferUshort function


## -description


The <b>VideoPortWriteRegisterBufferUshort</b> function writes a number of USHORT values to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Buffer [in]

Pointer to a buffer containing the USHORT values to be written.


### -param Count

Specifies the number of USHORT values to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterBufferUshort</b>.

Callers of <b>VideoPortWriteRegisterBufferUshort</b>can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

