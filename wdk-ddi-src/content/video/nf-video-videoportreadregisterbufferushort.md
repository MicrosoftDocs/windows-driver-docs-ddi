---
UID: NF:video.VideoPortReadRegisterBufferUshort
title: VideoPortReadRegisterBufferUshort function (video.h)
description: The VideoPortReadRegisterBufferUshort function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.
old-location: display\videoportreadregisterbufferushort.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortReadRegisterBufferUshort function"]
ms.keywords: VideoPortReadRegisterBufferUshort, VideoPortReadRegisterBufferUshort function [Display Devices], VideoPort_Functions_f10955b1-ab90-46dc-8e53-1c395af6f0bc.xml, display.videoportreadregisterbufferushort, video/VideoPortReadRegisterBufferUshort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortReadRegisterBufferUshort
 - video/VideoPortReadRegisterBufferUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReadRegisterBufferUshort
---

# VideoPortReadRegisterBufferUshort function


## -description

The <b>VideoPortReadRegisterBufferUshort</b> function reads a number of USHORT values from a mapped device memory range and writes them into a buffer.

## -parameters

### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Buffer [out]


Pointer to a buffer into which the USHORT values are written.

### -param Count

Specifies the number of USHORT values to be written to the buffer.

## -returns

None

## -remarks

The buffer must be large enough to contain at least the specified number of USHORT values.

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterBufferUshort</b>.

Callers of <b>VideoPortReadRegisterBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
