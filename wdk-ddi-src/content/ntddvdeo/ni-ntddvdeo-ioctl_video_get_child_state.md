---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_CHILD_STATE
title: IOCTL_VIDEO_GET_CHILD_STATE
description: Determines whether a child device is currently enabled.
old-location: display\ioctl_video_get_child_state.htm
tech.root: display
ms.assetid: 2b912f2d-2bb3-4f38-a415-a61900ad16fb
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_GET_CHILD_STATE, IOCTL_VIDEO_GET_CHILD_STATE control, IOCTL_VIDEO_GET_CHILD_STATE control code [Display Devices], Video_IOCTLs_5f13cbad-a5b4-41cb-8d93-dce6badfc8ce.xml, display.ioctl_video_get_child_state, ntddvdeo/IOCTL_VIDEO_GET_CHILD_STATE
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
-	IOCTL_VIDEO_GET_CHILD_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_GET_CHILD_STATE IOCTL


## -description



Determines whether a child device is currently enabled. Although miniport driver support for this modal request is optional, it is highly recommended. Otherwise, Windows 2000 and later must call the BIOS to perform the operation, which is very inefficient and can adversely affect system robustness. If the BIOS cannot handle this request, then Windows 2000 or later considers the child device to be active.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a pointer to a ULONG, containing the index of the child device, as specified in <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>.


### -input-buffer-length

### -output-buffer

The video miniport driver returns a ULONG in the VRP <b>OutputBuffer</b> that can be a combination of the following flags:

| **Value** | **Meaning** | 
|:--|:--|
| VIDEO_CHILD_ACTIVE | The child device is active. | 
| VIDEO_CHILD_DETACHED | The child device is detached from the view. This flag is used in DualView implementations to indicate the logical relationships of child devices. See [Supporting DualView (Windows 2000 Model)](https://msdn.microsoft.com/08da97c9-1d31-40f5-99df-5f16eaa47c79)  for more information. | 
| VIDEO_CHILD_NOPRUNE_FREQ | The child device can drive an image at any refresh rate, regardless of its EDID setting.<br/>This flag is used for mode pruning. By default, Windows 2000 and later perform mode pruning for each active child. When the miniport driver wants to prevent the operating system from performing mode pruning on specific child devices, however, it should use this flag. | 
| VIDEO_CHILD_NOPRUNE_SIZE | The child device can drive an image of any size, regardless of its EDID setting.<br/>This flag is used for mode pruning. By default, Windows 2000 and later perform mode pruning for each active child. When the miniport driver wants to prevent the operating system from performing mode pruning on specific child devices, however, it should use this flag. |

 
### -output-buffer-length

### -in-out-buffer


### -inout-buffer-length

### -status-block

The video miniport driver sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(ULONG).

## -see-also

<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

