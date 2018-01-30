---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_CHILD_STATE
title: IOCTL_VIDEO_GET_CHILD_STATE
author: windows-driver-content
description: Determines whether a child device is currently enabled.
old-location: display\ioctl_video_get_child_state.htm
old-project: display
ms.assetid: 2b912f2d-2bb3-4f38-a415-a61900ad16fb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_get_child_state, IOCTL_VIDEO_GET_CHILD_STATE control code [Display Devices], IOCTL_VIDEO_GET_CHILD_STATE, ntddvdeo/IOCTL_VIDEO_GET_CHILD_STATE, Video_IOCTLs_5f13cbad-a5b4-41cb-8d93-dce6badfc8ce.xml
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
-	IOCTL_VIDEO_GET_CHILD_STATE
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_GET_CHILD_STATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Determines whether a child device is currently enabled. Although miniport driver support for this modal request is optional, it is highly recommended. Otherwise, Windows 2000 and later must call the BIOS to perform the operation, which is very inefficient and can adversely affect system robustness. If the BIOS cannot handle this request, then Windows 2000 or later considers the child device to be active.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a pointer to a ULONG, containing the index of the child device, as specified in <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>.


### -input-buffer-length


<text></text>



### -output-buffer

The video miniport driver returns a ULONG in the VRP <b>OutputBuffer</b> that can be a combination of the following flags:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_CHILD_ACTIVE

</td>
<td>
The child device is active.

</td>
</tr>
<tr>
<td>
VIDEO_CHILD_DETACHED

</td>
<td>
The child device is detached from the view. This flag is used in DualView implementations to indicate the logical relationships of child devices. See <a href="https://msdn.microsoft.com/08da97c9-1d31-40f5-99df-5f16eaa47c79">Supporting DualView (Windows 2000 Model)</a>  for more information.

</td>
</tr>
<tr>
<td>
VIDEO_CHILD_NOPRUNE_FREQ

</td>
<td>
The child device can drive an image at any refresh rate, regardless of its EDID setting.

This flag is used for mode pruning. By default, Windows 2000 and later perform mode pruning for each active child. When the miniport driver wants to prevent the operating system from performing mode pruning on specific child devices, however, it should use this flag.

</td>
</tr>
<tr>
<td>
VIDEO_CHILD_NOPRUNE_SIZE

</td>
<td>
The child device can drive an image of any size, regardless of its EDID setting.

This flag is used for mode pruning. By default, Windows 2000 and later perform mode pruning for each active child. When the miniport driver wants to prevent the operating system from performing mode pruning on specific child devices, however, it should use this flag.

</td>
</tr>
</table> 


### -output-buffer-length


<text></text>



### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The video miniport driver sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(ULONG).


## -see-also

<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_GET_CHILD_STATE control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

