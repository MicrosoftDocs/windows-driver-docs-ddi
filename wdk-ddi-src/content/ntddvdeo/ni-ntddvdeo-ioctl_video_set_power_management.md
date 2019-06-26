---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_POWER_MANAGEMENT
title: IOCTL_VIDEO_SET_POWER_MANAGEMENT (ntddvdeo.h)
description: This IOCTL is obsolete in Windows 2000 and later, and is no longer supported.
old-location: display\ioctl_video_set_power_management.htm
tech.root: display
ms.assetid: 76b643db-318c-4dd4-bc45-e9da27ecb283
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_SET_POWER_MANAGEMENT, IOCTL_VIDEO_SET_POWER_MANAGEMENT control, IOCTL_VIDEO_SET_POWER_MANAGEMENT control code [Display Devices], Video_IOCTLs_36fe9d13-31c0-435c-939c-af0ce6d5b380.xml, display.ioctl_video_set_power_management, ntddvdeo/IOCTL_VIDEO_SET_POWER_MANAGEMENT
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_SET_POWER_MANAGEMENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_POWER_MANAGEMENT IOCTL


## -description



This IOCTL is <b>obsolete</b> in Windows 2000 and later, and is no longer supported. A Plug and Play video miniport driver should implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_power_set">HwVidSetPowerState</a> function, which provides similar functionality.

Resets the power-consumption level of the adapter to the specified state. As long as the state is <b>VideoPowerOff</b>, the port driver intercepts and fails all IOCTL_VIDEO_<i>XXX</i> requests to the miniport driver until the next IOCTL_VIDEO_SET_POWER_MANAGEMENT request that resets the state to a power-on condition.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a> structure, specifying the state to be set.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_status_block">STATUS_BLOCK</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_status_block">STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a>
 

 

