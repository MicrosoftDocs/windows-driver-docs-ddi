---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
title: IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
author: windows-driver-content
description: Performs a display device switch, a state change in which the video signal going to one display device is sent to another, possibly different type of display device.
old-location: display\ioctl_video_set_child_state_configuration.htm
tech.root: display
ms.assetid: ae70c0e5-0ce0-4e44-983c-9bc0f9a1f600
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION, IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION control, IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION control code [Display Devices], Video_IOCTLs_bd76ef78-623a-4f72-b0fd-1ac70b211a98.xml, display.ioctl_video_set_child_state_configuration, ntddvdeo/IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION IOCTL


## -description



Performs a display device switch, a state change in which the video signal going to one display device is sent to another, possibly different type of display device. After the display device switch, the video signal can be sent to one or both display devices. When the video port driver receives a notification to switch display devices, it sends this IOCTL to the miniport driver. Normally, this IOCTL is sent after <a href="https://msdn.microsoft.com/library/windows/hardware/ff568156">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a> indicates that the miniport driver is ready to make the switch. If the miniport driver is capable of switching display devices, it should do so and set the <b>Status</b> member of <b>StatusBlock</b> to NO_ERROR.

If the miniport driver is not capable of performing the display device switch, it can set the <b>Status</b> member of <b>StatusBlock</b> to an appropriate error value (described in the <b>StatusBlock</b> section), choosing not to handle the request. Although this request is optional, it is highly recommended that the miniport driver handle this request. Failure to do so forces a call to the BIOS to handle the display device switch, which can be very inefficient, and can have an adverse effect on the system's robustness. 

IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION is synchronous. After this IOCTL is sent, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567801">IOCTL_VIDEO_GET_CHILD_STATE</a> should reflect the new state. 

This request is modal.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a> structure.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver sets the <b>Status</b> member to NO_ERROR if it is capable of performing the display device switch. If it is not able to carry out this operation, the miniport driver can set <b>Status</b> to an appropriate error value, or do nothing at all.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567801">IOCTL_VIDEO_GET_CHILD_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568156">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a>
 

 

