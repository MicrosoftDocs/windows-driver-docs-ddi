---
UID: NF:video.VideoPortInitialize
title: VideoPortInitialize function (video.h)
description: The VideoPortInitialize function performs part of the miniport driver initialization, allocating system resources for the miniport driver.
old-location: display\videoportinitialize.htm
tech.root: display
ms.assetid: cc0da962-beeb-4035-a68e-e5b856cd5d9b
ms.date: 05/10/2018
keywords: ["VideoPortInitialize function"]
ms.keywords: VideoPortInitialize, VideoPortInitialize function [Display Devices], VideoPort_Functions_215d2fe2-98a9-4504-96cb-492370e349c8.xml, display.videoportinitialize, video/VideoPortInitialize
f1_keywords:
 - "video/VideoPortInitialize"
 - "VideoPortInitialize"
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
- VideoPortInitialize
targetos: Windows
req.typenames: 
---

# VideoPortInitialize function


## -description


The <b>VideoPortInitialize</b> function performs part of the miniport driver initialization, allocating system resources for the miniport driver.


## -parameters




### -param Argument1

A pointer with which the operating system called <a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-video-miniport-driver">DriverEntry of Video Miniport Driver</a>.


### -param Argument2

A second pointer with which the operating system called <b>DriverEntry</b>.


### -param HwInitializationData

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure on the stack. The miniport driver's <b>DriverEntry</b> routine zero-initialized this structure and then filled it in with driver-specific configuration information describing a video adapter that the miniport driver can support.


### -param HwContext

Must be <b>NULL</b>.


## -returns



<b>VideoPortInitialize</b> returns the final status of the initialization operation. 




## -remarks



Every video miniport driver must call <b>VideoPortInitialize</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function. <b>DriverEntry</b> can call <b>VideoPortInitialize</b> only after it has first zero-initialized and then set up the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure. <b>VideoPortInitialize</b> can be called only from a miniport driver's <b>DriverEntry</b> function.

The <b>VideoPortInitialize</b> function:

<ul>
<li>
Checks the validity of the miniport driver's VIDEO_HW_INITIALIZATION_DATA specifications.

</li>
<li>
Allocates memory for and zero-initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure.

</li>
<li>
Fills in as much adapter configuration information as it can in VIDEO_PORT_CONFIG_INFO.

</li>
<li>
Fills in some of the public members of the device object created by the system to represent the graphics adapter. The video port driver manages the device objects, therefore, the miniport driver need not be concerned with device object details.

</li>
<li>
Allocates memory for, and zero-initializes the device extension of, the device object. A <i>device extension </i>is each miniport driver's primary and only global storage area for adapter-specific state information. The miniport driver specifies the size of the device extension in the <b>HwDeviceExtensionSize</b> member of VIDEO_HW_INITIALIZATION_DATA. The video port driver passes this device extension to most of the miniport driver functions that it calls.

</li>
<li>
Collects and stores pertinent information in the device extension.

</li>
</ul>
The miniport driver's <b>DriverEntry</b> routine propagates the value returned by <b>VideoPortInitialize</b> back to its caller. Miniport drivers should not use this return value. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-video-miniport-driver">DriverEntry of Video Miniport Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_initialize">HwVidInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzeromemory">VideoPortZeroMemory</a>
 

 

