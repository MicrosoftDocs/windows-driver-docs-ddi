---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURRENT_MODE
title: IOCTL_VIDEO_SET_CURRENT_MODE
author: windows-driver-content
description: Sets the adapter to the specified operating mode.
old-location: display\ioctl_video_set_current_mode.htm
old-project: display
ms.assetid: 7dd77e55-01d7-4e10-8134-813fe0c1fc6c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_SET_CURRENT_MODE, IOCTL_VIDEO_SET_CURRENT_MODE control code [Display Devices], Video_IOCTLs_df8e3e45-0a72-427b-b47f-49bc936d53a5.xml, display.ioctl_video_set_current_mode, ntddvdeo/IOCTL_VIDEO_SET_CURRENT_MODE
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
-	IOCTL_VIDEO_SET_CURRENT_MODE
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_CURRENT_MODE IOCTL


## -description



Sets the adapter to the specified operating mode. Miniport drivers are required to support this nonmodal request because it resets the current mode. The miniport driver must also consider the two high order flags which are used to additionally control the mode set operation. See <a href="..\ntddvdeo\ns-ntddvdeo-_video_mode.md">VIDEO_MODE</a> for further information.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_mode.md">VIDEO_MODE</a> structure specifying the mode to be set.


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

The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## -see-also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_mode.md">VIDEO_MODE</a>



 

 


