---
UID: NS:video._VIDEO_CHILD_STATE_CONFIGURATION
title: _VIDEO_CHILD_STATE_CONFIGURATION (video.h)
description: The VIDEO_CHILD_STATE_CONFIGURATION structure contains an array of VIDEO_CHILD_STATE structures, each holding the state of a particular child device.
old-location: display\video_child_state_configuration.htm
tech.root: display
ms.assetid: e298ef49-d285-426a-9028-78f7f54340b2
ms.date: 05/10/2018
keywords: ["VIDEO_CHILD_STATE_CONFIGURATION structure"]
ms.keywords: "*PVIDEO_CHILD_STATE_CONFIGURATION, PVIDEO_CHILD_STATE_CONFIGURATION, PVIDEO_CHILD_STATE_CONFIGURATION structure pointer [Display Devices], VIDEO_CHILD_STATE_CONFIGURATION, VIDEO_CHILD_STATE_CONFIGURATION structure [Display Devices], Video_Structs_22fa1242-c537-4cae-ab47-b7e972e24d09.xml, _VIDEO_CHILD_STATE_CONFIGURATION, display.video_child_state_configuration, video/PVIDEO_CHILD_STATE_CONFIGURATION, video/VIDEO_CHILD_STATE_CONFIGURATION"
f1_keywords:
 - "video/VIDEO_CHILD_STATE_CONFIGURATION"
 - "VIDEO_CHILD_STATE_CONFIGURATION"
req.header: video.h
req.include-header: Video.h
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
- video.h
api_name:
- VIDEO_CHILD_STATE_CONFIGURATION
targetos: Windows
req.typenames: VIDEO_CHILD_STATE_CONFIGURATION, *PVIDEO_CHILD_STATE_CONFIGURATION
---

# _VIDEO_CHILD_STATE_CONFIGURATION structure


## -description


The VIDEO_CHILD_STATE_CONFIGURATION structure contains an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_child_state">VIDEO_CHILD_STATE</a> structures, each holding the state of a particular child device.


## -struct-fields




### -field Count

Specifies the number of structures in the <b>ChildStateArray</b> member.


### -field ChildStateArray

Is an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_child_state">VIDEO_CHILD_STATE</a> structures. Each element of this array contains the ID and state for a particular child device.


## -remarks



The video port driver sends a VIDEO_CHILD_STATE_CONFIGURATION structure to the miniport driver for the following IOCTLs:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_validate_child_state_configuration">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>, in which the video port driver queries the miniport driver to determine whether the specified state for each child device in <b>ChildStateArray</b> is valid.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_child_state_configuration">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>, in which the video port driver requests the miniport driver to make the specified state change for each child device in <b>ChildStateArray</b>.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_child_state_configuration">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_validate_child_state_configuration">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_child_state">VIDEO_CHILD_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>
 

 

