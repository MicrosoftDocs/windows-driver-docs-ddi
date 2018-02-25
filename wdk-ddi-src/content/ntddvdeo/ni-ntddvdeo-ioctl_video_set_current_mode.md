---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURRENT_MODE
title: IOCTL_VIDEO_SET_CURRENT_MODE
author: windows-driver-content
description: Sets the adapter to the specified operating mode.
old-location: display\ioctl_video_set_current_mode.htm
old-project: display
ms.assetid: 7dd77e55-01d7-4e10-8134-813fe0c1fc6c
ms.author: windowsdriverdev
ms.date: 2/22/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_SET_CURRENT_MODE
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_CURRENT_MODE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SET_CURRENT_MODE control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

