---
UID: NC:dispmprt.DXGK_BRIGHTNESS_SET
title: DXGK_BRIGHTNESS_SET (dispmprt.h)
description: The DxgkDdiSetBrightness function sets a new brightness level.
old-location: display\dxgkddisetbrightness.htm
tech.root: display
ms.assetid: 83609679-20df-463d-ac3a-bb8a87897608
ms.date: 05/10/2018
keywords: ["DXGK_BRIGHTNESS_SET callback function"]
ms.keywords: DXGK_BRIGHTNESS_SET, DXGK_BRIGHTNESS_SET callback, DmFunctions_7b5ff27a-7a8f-4dee-8b3d-c9b0df76db6d.xml, DxgkDdiSetBrightness, DxgkDdiSetBrightness callback function [Display Devices], display.dxgkddisetbrightness, dispmprt/DxgkDdiSetBrightness
f1_keywords:
 - "dispmprt/DxgkDdiSetBrightness"
 - "DxgkDdiSetBrightness"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkDdiSetBrightness
targetos: Windows
req.typenames: 
---

# DXGK_BRIGHTNESS_SET callback function


## -description


The <i>DxgkDdiSetBrightness</i> function sets a new brightness level. 


## -parameters




### -param Context 
[in]
A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param Brightness 
[in]
The brightness level value to set.


## -returns



<i>DxgkDdiSetBrightness</i> returns STATUS_SUCCESS if it succeeds in setting a new brightness level. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>. 




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/display/monitor-drivers">monitor driver</a> calls the display miniport driver's <i>DxgkDdiSetBrightness</i> function to change the brightness level of the integrated display panel for the following reasons:

<ul>
<li>
Notifications from the Device Power Policy Engine (DPPE) indicate that either the current policy is modified or a new policy takes effect. A new DPPE policy takes effect on system start, resume, and user switch, as well as when the power source is changed.

</li>
<li>
The preferred way for user-mode clients to control brightness is through Windows Management Instrumentation (WMI). The monitor driver implements the WMI brightness controls that select a brightness level or revert the brightness level to the level that was selected by the currently active DPPE policy. The WMI method to select a brightness level overrides the current DPPE policy level until any change in DPPE policy occurs. When DPPE policy changes, the new DPPE level is set. 

</li>
<li>
For compatibility with the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/windows-2000-display-driver-model-design-guide">Windows 2000 Display Driver Model</a>, the monitor driver implements <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_display_brightness">IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS</a> as an alternative way for user-mode clients to control brightness. A call to IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS is handled the same way as the WMI brightness control that selects a brightness level. 

</li>
<li>
The monitor driver interprets brightness hot-key notifications from the Advanced Configuration and Power Interface (ACPI) driver as user requests to change the current brightness level. As with the WMI and IOCTL user-mode interfaces, a change in brightness level that is triggered by a hot-key notification overrides the current DPPE policy and stays in effect until DPPE policy requests that the brightness value is set again.

</li>
</ul>
<i>DxgkDdiSetBrightness</i> should be made pageable. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_display_brightness">IOCTL_VIDEO_SET_DISPLAY_BRIGHTNESS</a>
 

 

