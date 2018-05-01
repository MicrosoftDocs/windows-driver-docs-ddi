---
UID: NC:video.PVIDEO_HW_POWER_GET
title: PVIDEO_HW_POWER_GET
author: windows-driver-content
description: HwVidGetPowerState queries whether the device can support the requested power state.
old-location: display\hwvidgetpowerstate.htm
old-project: display
ms.assetid: 747cfbfb-2a38-4a0d-b8c6-662d0c3967ba
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: HwVidGetPowerState, HwVidGetPowerState callback function [Display Devices], PVIDEO_HW_POWER_GET, PVIDEO_HW_POWER_GET callback, VideoMiniport_Functions_b47b2224-5e0b-44af-9d04-107ff1299381.xml, display.hwvidgetpowerstate, video/HwVidGetPowerState
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
-	HwVidGetPowerState
product: Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_POWER_GET callback function


## -description


<i>HwVidGetPowerState</i> queries whether the device can support the requested power state.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param HwId

Pointer to a 32-bit <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device ID</a> that uniquely identifies the device that the miniport driver should query. This parameter is returned by the miniport driver's <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function. Alternatively, a value of DISPLAY_ADAPTER_HW_ID indicates that power information is being requested of the adapter itself.


### -param VideoPowerControl

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state for which support is being queried.


## -returns



<i>HwVidGetPowerState</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR </b></dt>
</dl>
</td>
<td width="60%">
The device supports the requested power state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_DEVICE_REINITIALIZATION_NEEDED</b></dt>
</dl>
</td>
<td width="60%">
The driver failed the power state query.

</td>
</tr>
</table>
 




## -remarks



<i>HwVidGetPowerState</i> is a required function in a video miniport driver.

The driver should check the ID specified in <i>HwId</i> to determine which device to query. The driver should then determine whether that device supports the power state specified in the <b>PowerState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure to which <i>VideoPowerControl</i> points.

This function must not return the current power state of the device.

<i>HwVidGetPowerState</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a>
 

 

