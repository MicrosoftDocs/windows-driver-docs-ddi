---
UID: NF:video.VideoPortWriteRegisterUshort
title: VideoPortWriteRegisterUshort function (video.h)
description: The VideoPortWriteRegisterUshort function writes a USHORT value to a mapped register.
old-location: display\videoportwriteregisterushort.htm
tech.root: display
ms.assetid: 0bc9b0a1-6cd8-4d76-a71e-694a8435773e
ms.date: 05/10/2018
keywords: ["VideoPortWriteRegisterUshort function"]
ms.keywords: VideoPortWriteRegisterUshort, VideoPortWriteRegisterUshort function [Display Devices], VideoPort_Functions_b7adcb2e-bf7a-4ce3-bcd9-f11c24982b48.xml, display.videoportwriteregisterushort, video/VideoPortWriteRegisterUshort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortWriteRegisterUshort
 - video/VideoPortWriteRegisterUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortWriteRegisterUshort
---

# VideoPortWriteRegisterUshort function


## -description

The <b>VideoPortWriteRegisterUshort</b> function writes a USHORT value to a mapped register.

## -parameters

### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Value

Specifies a USHORT value to be transferred to the adapter.

## -returns

None

## -remarks

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUshort</b>.

Callers of <b>VideoPortWriteRegisterUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>

