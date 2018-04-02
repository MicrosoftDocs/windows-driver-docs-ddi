---
UID: NC:video.PVIDEO_HW_POWER_SET
title: PVIDEO_HW_POWER_SET
author: windows-driver-content
description: HwVidSetPowerState sets the power state of the specified device.
old-location: display\hwvidsetpowerstate.htm
old-project: display
ms.assetid: d7800ab6-9d8f-47a7-b919-8b6b0197d163
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HwVidSetPowerState, HwVidSetPowerState callback function [Display Devices], PVIDEO_HW_POWER_SET, VideoMiniport_Functions_22a6c5ae-0c31-48a6-8882-06edfea32c1a.xml, display.hwvidsetpowerstate, video/HwVidSetPowerState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidSetPowerState
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_HW_POWER_SET callback


## -description


<i>HwVidSetPowerState</i> sets the power state of the specified device.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param HwId

Pointer to a 32-bit <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device ID</a> that uniquely identifies the device for which the miniport driver should set the power state. This parameter is the value returned by the miniport driver's <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function. A value of DISPLAY_ADAPTER_HW_ID indicates that the miniport driver should set the power state of the adapter itself.


### -param VideoPowerControl

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state to be set.


## -returns



<i>HwVidSetPowerState</i> should always return NO_ERROR.




## -remarks



<i>HwVidSetPowerState</i> is a required function in a video miniport driver.

The driver should check the ID specified in <i>HwId</i> to determine the device on which to set the power state. The driver should then set that device's power state to the level specified in the <b>PowerState</b> member of the VIDEO_POWER_MANAGEMENT structure to which <i>VideoPowerControl</i> points.

<i>HwVidSetPowerState</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a>



<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a>
 

 

