---
UID: NI:ntddvdeo.IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
title: IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION (ntddvdeo.h)
description: Queries the miniport driver to determine whether it is ready for a display device switch.
old-location: display\ioctl_video_validate_child_state_configuration.htm
tech.root: display
ms.assetid: 18ab1aeb-e1a8-4c62-8c34-4ea534742342
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION IOCTL"]
ms.keywords: IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION, IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION control, IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION control code [Display Devices], Video_IOCTLs_8e2a488b-85d7-4814-b85b-a96162fe5963.xml, display.ioctl_video_validate_child_state_configuration, ntddvdeo/IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
 - ntddvdeo/IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION
---

# IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION IOCTL


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
The video miniport driver carries out a validated display device switch when it receives an <a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_child_state_configuration">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a> request.

The miniport driver is not required to handle this modal IOCTL. The video port driver interprets a default return value from the miniport driver as permission to proceed with the display device switch.

## -ioctlparameters

### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_child_state_configuration">VIDEO_CHILD_STATE_CONFIGURATION</a> structure.

### -input-buffer-length

### -output-buffer

The miniport driver returns 1 in the VRP <b>OutputBuffer</b> if the video port driver should proceed with the display device switch; otherwise, the driver returns 0 in the VRP <b>OutputBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver stores NO_ERROR in <b>Status</b> if it has successfully handled this IOCTL; otherwise, the driver stores a relevant video error code in <b>Status</b>. In either case, the miniport driver sets the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(ULONG).

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_child_state_configuration">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_child_state_configuration">VIDEO_CHILD_STATE_CONFIGURATION</a>