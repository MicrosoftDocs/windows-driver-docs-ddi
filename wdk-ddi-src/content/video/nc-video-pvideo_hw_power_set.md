---
UID: NC:video.PVIDEO_HW_POWER_SET
title: PVIDEO_HW_POWER_SET (video.h)
description: HwVidSetPowerState sets the power state of the specified device.
old-location: display\hwvidsetpowerstate.htm
tech.root: display
ms.assetid: d7800ab6-9d8f-47a7-b919-8b6b0197d163
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_POWER_SET callback function"]
ms.keywords: HwVidSetPowerState, HwVidSetPowerState callback function [Display Devices], PVIDEO_HW_POWER_SET, PVIDEO_HW_POWER_SET callback, VideoMiniport_Functions_22a6c5ae-0c31-48a6-8882-06edfea32c1a.xml, display.hwvidsetpowerstate, video/HwVidSetPowerState
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PVIDEO_HW_POWER_SET
 - video/PVIDEO_HW_POWER_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - HwVidSetPowerState
---

# PVIDEO_HW_POWER_SET callback function


## -description

<i>HwVidSetPowerState</i> sets the power state of the specified device.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.

### -param HwId

Pointer to a 32-bit <a href="https://docs.microsoft.com/windows-hardware/drivers/">device ID</a> that uniquely identifies the device for which the miniport driver should set the power state. This parameter is the value returned by the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a> function. A value of DISPLAY_ADAPTER_HW_ID indicates that the miniport driver should set the power state of the adapter itself.

### -param VideoPowerControl

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state to be set.

## -returns

<i>HwVidSetPowerState</i> should always return NO_ERROR.

## -remarks

<i>HwVidSetPowerState</i> is a required function in a video miniport driver.

The driver should check the ID specified in <i>HwId</i> to determine the device on which to set the power state. The driver should then set that device's power state to the level specified in the <b>PowerState</b> member of the VIDEO_POWER_MANAGEMENT structure to which <i>VideoPowerControl</i> points.

<i>HwVidSetPowerState</i> should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_power_get">HwVidGetPowerState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a>

