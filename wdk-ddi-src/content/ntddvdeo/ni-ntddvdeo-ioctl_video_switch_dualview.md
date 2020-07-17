---
UID: NI:ntddvdeo.IOCTL_VIDEO_SWITCH_DUALVIEW
title: IOCTL_VIDEO_SWITCH_DUALVIEW (ntddvdeo.h)
description: Notifies the video miniport that a secondary view is about to be enabled or disabled.
old-location: display\ioctl_video_switch_dualview.htm
tech.root: display
ms.assetid: 09fe033f-7876-4b23-baf6-5afe0866bb1d
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SWITCH_DUALVIEW IOCTL"]
ms.keywords: IOCTL_VIDEO_SWITCH_DUALVIEW, IOCTL_VIDEO_SWITCH_DUALVIEW control, IOCTL_VIDEO_SWITCH_DUALVIEW control code [Display Devices], Video_IOCTLs_424b313b-2f68-4284-97d6-596f1407ee96.xml, display.ioctl_video_switch_dualview, ntddvdeo/IOCTL_VIDEO_SWITCH_DUALVIEW
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_SWITCH_DUALVIEW"
 - "IOCTL_VIDEO_SWITCH_DUALVIEW"
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
- IOCTL_VIDEO_SWITCH_DUALVIEW
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SWITCH_DUALVIEW IOCTL


## -description



Notifies the video miniport that a secondary view is about to be enabled or disabled. A secondary view is enabled by a call to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcreatesecondarydisplay">VideoPortCreateSecondaryDisplay</a>.

Windows XP and later send this request to the video miniport driver to notify it of a secondary view change of status. Video miniport drivers can use this notification to make video memory arrangements in advance. For example, when the display driver sets the mode of the primary view, it can reserve video memory for one or more secondary views. 

<div class="alert"><b>Note</b>    This request, which is available in Windows XP and later, can only be used to manage video memory.</div>
<div> </div>



## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a pointer to a ULONG, which can be one of the two following values:

|Value|Meaning|
|--- |--- |
|0|The device is about to be detached.|
|1|The device is about to be attached.|
 

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length


### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcreatesecondarydisplay">VideoPortCreateSecondaryDisplay</a>
 

 

