---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
title: IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
author: windows-driver-content
description: Performs a display device switch, a state change in which the video signal going to one display device is sent to another, possibly different type of display device.
old-location: display\ioctl_video_set_child_state_configuration.htm
old-project: display
ms.assetid: ae70c0e5-0ce0-4e44-983c-9bc0f9a1f600
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION, IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION control code [Display Devices], Video_IOCTLs_bd76ef78-623a-4f72-b0fd-1ac70b211a98.xml, display.ioctl_video_set_child_state_configuration, ntddvdeo/IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION
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
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Performs a display device switch, a state change in which the video signal going to one display device is sent to another, possibly different type of display device. After the display device switch, the video signal can be sent to one or both display devices. When the video port driver receives a notification to switch display devices, it sends this IOCTL to the miniport driver. Normally, this IOCTL is sent after <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_validate_child_state_configuration.md">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a> indicates that the miniport driver is ready to make the switch. If the miniport driver is capable of switching display devices, it should do so and set the <b>Status</b> member of <b>StatusBlock</b> to NO_ERROR.

If the miniport driver is not capable of performing the display device switch, it can set the <b>Status</b> member of <b>StatusBlock</b> to an appropriate error value (described in the <b>StatusBlock</b> section), choosing not to handle the request. Although this request is optional, it is highly recommended that the miniport driver handle this request. Failure to do so forces a call to the BIOS to handle the display device switch, which can be very inefficient, and can have an adverse effect on the system's robustness. 

IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION is synchronous. After this IOCTL is sent, <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_get_child_state.md">IOCTL_VIDEO_GET_CHILD_STATE</a> should reflect the new state. 

This request is modal.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="..\video\ns-video-_video_child_state_configuration.md">VIDEO_CHILD_STATE_CONFIGURATION</a> structure.


### -input-buffer-length



<text></text>




### -output-buffer

None


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The miniport driver sets the <b>Status</b> member to NO_ERROR if it is capable of performing the display device switch. If it is not able to carry out this operation, the miniport driver can set <b>Status</b> to an appropriate error value, or do nothing at all.


## -see-also

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_validate_child_state_configuration.md">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>



<a href="..\video\ns-video-_video_child_state_configuration.md">VIDEO_CHILD_STATE_CONFIGURATION</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_get_child_state.md">IOCTL_VIDEO_GET_CHILD_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

