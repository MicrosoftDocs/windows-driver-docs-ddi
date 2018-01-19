---
UID: NI:ntddvdeo.IOCTL_VIDEO_SWITCH_DUALVIEW
title: IOCTL_VIDEO_SWITCH_DUALVIEW
author: windows-driver-content
description: Notifies the video miniport that a secondary view is about to be enabled or disabled.
old-location: display\ioctl_video_switch_dualview.htm
old-project: display
ms.assetid: 09fe033f-7876-4b23-baf6-5afe0866bb1d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
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
req.alt-api: IOCTL_VIDEO_SWITCH_DUALVIEW
req.alt-loc: Ntddvdeo.h
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
req.typenames: *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SWITCH_DUALVIEW IOCTL



## -description

Notifies the video miniport that a secondary view is about to be enabled or disabled. A secondary view is enabled by a call to the video port driver's <a href="..\video\nf-video-videoportcreatesecondarydisplay.md">VideoPortCreateSecondaryDisplay</a>.

Windows XP and later send this request to the video miniport driver to notify it of a secondary view change of status. Video miniport drivers can use this notification to make video memory arrangements in advance. For example, when the display driver sets the mode of the primary view, it can reserve video memory for one or more secondary views. 

<div class="alert"><b>Note</b>    This request, which is available in Windows XP and later, can only be used to manage video memory.</div>
<div> </div>


Notifies the video miniport that a secondary view is about to be enabled or disabled. A secondary view is enabled by a call to the video port driver's <a href="..\video\nf-video-videoportcreatesecondarydisplay.md">VideoPortCreateSecondaryDisplay</a>.

Windows XP and later send this request to the video miniport driver to notify it of a secondary view change of status. Video miniport drivers can use this notification to make video memory arrangements in advance. For example, when the display driver sets the mode of the primary view, it can reserve video memory for one or more secondary views. 



## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains a pointer to a ULONG, which can be one of the two following values:

0

The device is about to be detached.

1

The device is about to be attached.

 


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
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\video\nf-video-videoportcreatesecondarydisplay.md">VideoPortCreateSecondaryDisplay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SWITCH_DUALVIEW control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

