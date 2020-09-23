---
UID: NC:video.PVIDEO_HW_POWER_GET
title: PVIDEO_HW_POWER_GET (video.h)
description: HwVidGetPowerState queries whether the device can support the requested power state.
old-location: display\hwvidgetpowerstate.htm
tech.root: display
ms.assetid: 747cfbfb-2a38-4a0d-b8c6-662d0c3967ba
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_POWER_GET callback function"]
ms.keywords: HwVidGetPowerState, HwVidGetPowerState callback function [Display Devices], PVIDEO_HW_POWER_GET, PVIDEO_HW_POWER_GET callback, VideoMiniport_Functions_b47b2224-5e0b-44af-9d04-107ff1299381.xml, display.hwvidgetpowerstate, video/HwVidGetPowerState
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
 - PVIDEO_HW_POWER_GET
 - video/PVIDEO_HW_POWER_GET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - HwVidGetPowerState
---

# PVIDEO_HW_POWER_GET callback function


## -description

<i>HwVidGetPowerState</i> queries whether the device can support the requested power state.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.

### -param HwId

Pointer to a 32-bit <a href="/windows-hardware/drivers/">device ID</a> that uniquely identifies the device that the miniport driver should query. This parameter is returned by the miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a> function. Alternatively, a value of DISPLAY_ADAPTER_HW_ID indicates that power information is being requested of the adapter itself.

### -param VideoPowerControl

Pointer to a <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state for which support is being queried.

## -returns

<i>HwVidGetPowerState</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|NO_ERROR|The device supports the requested power state.|
|ERROR_DEVICE_REINITIALIZATION_NEEDED|The driver failed the power state query.|

## -remarks

<i>HwVidGetPowerState</i> is a required function in a video miniport driver.

The driver should check the ID specified in <i>HwId</i> to determine which device to query. The driver should then determine whether that device supports the power state specified in the <b>PowerState</b> member of the <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a> structure to which <i>VideoPowerControl</i> points.

This function must not return the current power state of the device.

<i>HwVidGetPowerState</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_power_set">HwVidSetPowerState</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a>