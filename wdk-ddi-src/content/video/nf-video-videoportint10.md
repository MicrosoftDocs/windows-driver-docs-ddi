---
UID: NF:video.VideoPortInt10
title: VideoPortInt10 function (video.h)
description: The VideoPortInt10 function performs the equivalent of an MS-DOS INT10 operation, such as setting the video mode. VideoPortInt10 runs the BIOS ROM code on the device.
old-location: display\videoportint10.htm
tech.root: display
ms.assetid: 5743d84c-6132-4058-b517-250b5de9a6b5
ms.date: 05/10/2018
ms.keywords: VideoPortInt10, VideoPortInt10 function [Display Devices], VideoPort_Functions_681fc4cc-f8f5-4d26-b3eb-8f4098339470.xml, display.videoportint10, video/VideoPortInt10
f1_keywords:
 - "video/VideoPortInt10"
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
- VideoPortInt10
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortInt10 function


## -description


The <b>VideoPortInt10</b> function performs the equivalent of an MS-DOS INT10 operation, such as setting the video mode. <b>VideoPortInt10</b> runs the BIOS ROM code on the device.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param BiosArguments

Pointer to a structure containing values for the x86 registers that should be set before making the BIOS call. The miniport driver should set any unused registers to zero. All values set up in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_x86_bios_arguments">VIDEO_x86_BIOS_ARGUMENTS</a> structure are interpreted as immediate values.


## -returns



<b>VideoPortInt10</b> returns NO_ERROR if it successfully called the given BIOS INT10 routine; otherwise, it returns an error status.




## -remarks



Generally, VGA-compatible miniport drivers, which support full-screen MS-DOS applications on x86-based machines, call <b>VideoPortInt10</b>. Such a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> function must have set up the <b>VdmPhysicalVideoMemoryAddress</b> and <b>VdmPhysicalVideoMemoryLength</b> for the range in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure.

However, other video miniport drivers also can call this function.

Because <b>VideoPortInt10</b> interprets the <i>BiosArgument</i> parameter values as immediate values, the caller cannot pass in or retrieve data from a memory buffer with this function. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_x86_bios_arguments">VIDEO_x86_BIOS_ARGUMENTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

