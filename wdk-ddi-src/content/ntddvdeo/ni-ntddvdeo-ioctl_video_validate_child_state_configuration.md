---
UID: NI:ntddvdeo.IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
title: IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
author: windows-driver-content
description: Queries the miniport driver to determine whether it is ready for a display device switch.
old-location: display\ioctl_video_validate_child_state_configuration.htm
old-project: display
ms.assetid: 18ab1aeb-e1a8-4c62-8c34-4ea534742342
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_validate_child_state_configuration, IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION control code [Display Devices], IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION, ntddvdeo/IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION, Video_IOCTLs_8e2a488b-85d7-4814-b85b-a96162fe5963.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Queries the miniport driver to determine whether it is ready for a display device switch. This switch is a state change in which the video signal going to one display device is sent to another, possibly different type of display device. After the display device switch, the video signal can be sent to one or both display devices. When the video port driver receives a request to switch display devices (by, for example, a hotkey being pressed), it sends this IOCTL to the video miniport driver. The value returned by the miniport driver indicates whether the video port driver should proceed with the display device switch. 

When the miniport driver receives this request, it should indicate that it has successfully handled the request by:

<ul>
<li>
Placing the appropriate value (described in the <b>Output</b> section) in <b>OutputBuffer</b>

</li>
<li>
Returning NO_ERROR in the <b>Status</b> member of the VRP's <b>StatusBlock</b>

</li>
</ul>
The video miniport driver carries out a validated display device switch when it receives an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_child_state_configuration.md">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a> request.

The miniport driver is not required to handle this modal IOCTL. The video port driver interprets a default return value from the miniport driver as permission to proceed with the display device switch.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="..\video\ns-video-_video_child_state_configuration.md">VIDEO_CHILD_STATE_CONFIGURATION</a> structure.


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns 1 in the VRP <b>OutputBuffer</b> if the video port driver should proceed with the display device switch; otherwise, the driver returns 0 in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The miniport driver stores NO_ERROR in <b>Status</b> if it has successfully handled this IOCTL; otherwise, the driver stores a relevant video error code in <b>Status</b>. In either case, the miniport driver sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(ULONG).


## -see-also

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_child_state_configuration.md">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>



<a href="..\video\ns-video-_video_child_state_configuration.md">VIDEO_CHILD_STATE_CONFIGURATION</a>



<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

