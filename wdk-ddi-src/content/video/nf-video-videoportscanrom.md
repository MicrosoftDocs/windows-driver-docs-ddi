---
UID: NF:video.VideoPortScanRom
title: VideoPortScanRom function (video.h)
description: The VideoPortScanRom function is obsolete in Windows XP and later versions. It is supported only for backward compatibility. VideoPortScanRom performs a case-sensitive search for a specified string in ROM.
old-location: display\videoportscanrom.htm
tech.root: display
ms.assetid: 7787237c-5afd-46f2-ac75-6c0b41d37352
ms.date: 05/10/2018
ms.keywords: VideoPortScanRom, VideoPortScanRom function [Display Devices], VideoPort_Functions_7bcf750d-48d5-4b3b-911f-90efd1f0eed1.xml, display.videoportscanrom, video/VideoPortScanRom
ms.topic: function
f1_keywords:
 - "video/VideoPortScanRom"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortScanRom
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortScanRom function


## -description


The <b>VideoPortScanRom</b> function is <b>obsolete</b> in Windows XP and later versions. It is supported only for backward compatibility. 

<b>VideoPortScanRom</b> performs a case-sensitive search for a specified string in ROM.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param RomBase

Specifies the base ROM address at which the search should start. The given <i>RomBase</i> must be in a mapped range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param RomLength

Specifies the size in bytes of the mapped ROM to be searched.


### -param String

Pointer to the driver-allocated string to search for.


## -returns



If the string is found, <b>VideoPortScanRom</b> returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.




## -remarks



<b>VideoPortScanRom</b> cannot be called from a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a> functions, or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>, or from a callback to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetromimage">VideoPortGetRomImage</a>
 

 

