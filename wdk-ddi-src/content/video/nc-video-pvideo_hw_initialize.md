---
UID: NC:video.PVIDEO_HW_INITIALIZE
title: PVIDEO_HW_INITIALIZE (video.h)
description: HwVidInitialize performs the first initialization of the adapter, after the HAL has given up control of the video hardware to the video port driver.
old-location: display\hwvidinitialize.htm
tech.root: display
ms.assetid: 0e43de21-59e5-4368-8ea2-34fa52e99950
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_INITIALIZE callback function"]
ms.keywords: HwVidInitialize, HwVidInitialize callback function [Display Devices], PVIDEO_HW_INITIALIZE, PVIDEO_HW_INITIALIZE callback, VideoMiniport_Functions_7c9d848d-8129-45cc-91f0-7f66f536e7a6.xml, display.hwvidinitialize, video/HwVidInitialize
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
 - PVIDEO_HW_INITIALIZE
 - video/PVIDEO_HW_INITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - HwVidInitialize
---

# PVIDEO_HW_INITIALIZE callback function


## -description

<i>HwVidInitialize</i> performs the first initialization of the adapter, after the HAL has given up control of the video hardware to the video port driver.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.

## -returns

If the initialization succeeds, <i>HwVidInitialize</i> returns <b>TRUE</b>.

## -remarks

Every video miniport driver must have a <i>HwVidInitialize</i> function.

The video port driver calls <i>HwVidInitialize</i> in response to an open request by the corresponding display driver. As soon as <i>HwVidInitialize</i> is called, the miniport driver can change the state of the adapter, unlike the miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> function, which must leave the adapter in VGA mode. On return from <i>HwVidInitialize</i>, the adapter must be initialized to a state equivalent to that set up by the miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_reset_hw">HwVidResetHw</a> function. This feature is used by autodetection to get mode information from the miniport driver.

If at all possible, <i>HwVidInitialize</i> should avoid programming the device hardware. The miniport driver will initialize the device later, when it is instructed to switch display modes.

<i>HwVidInitialize</i> should be made pageable.

## -see-also

<a href="/windows/win32/api/winddi/nf-winddi-drvassertmode">DrvAssertMode</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_reset_hw">HwVidResetHw</a>