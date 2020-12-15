---
UID: NF:video.VideoPortScanRom
title: VideoPortScanRom function (video.h)
description: The VideoPortScanRom function is obsolete in Windows XP and later versions. It is supported only for backward compatibility. VideoPortScanRom performs a case-sensitive search for a specified string in ROM.
old-location: display\videoportscanrom.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortScanRom function"]
ms.keywords: VideoPortScanRom, VideoPortScanRom function [Display Devices], VideoPort_Functions_7bcf750d-48d5-4b3b-911f-90efd1f0eed1.xml, display.videoportscanrom, video/VideoPortScanRom
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortScanRom
 - video/VideoPortScanRom
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortScanRom
---

# VideoPortScanRom function


## -description

The <b>VideoPortScanRom</b> function is <b>obsolete</b> in Windows XP and later versions. It is supported only for backward compatibility. 

<b>VideoPortScanRom</b> performs a case-sensitive search for a specified string in ROM.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param RomBase

Specifies the base ROM address at which the search should start. The given <i>RomBase</i> must be in a mapped range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param RomLength

Specifies the size in bytes of the mapped ROM to be searched.

### -param String

Pointer to the driver-allocated string to search for.

## -returns

If the string is found, <b>VideoPortScanRom</b> returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.

## -remarks

<b>VideoPortScanRom</b> cannot be called from a miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a> functions, or from <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>, or from a callback to <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetromimage">VideoPortGetRomImage</a>
