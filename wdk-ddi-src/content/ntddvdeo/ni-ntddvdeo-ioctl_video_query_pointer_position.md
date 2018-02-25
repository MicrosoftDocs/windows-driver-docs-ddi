---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_POSITION
title: IOCTL_VIDEO_QUERY_POINTER_POSITION
author: windows-driver-content
description: Returns the current position of the pointer. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_position.htm
old-project: display
ms.assetid: 0dbca53e-5fe0-4435-9f94-45601fbbf950
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_VIDEO_QUERY_POINTER_POSITION, IOCTL_VIDEO_QUERY_POINTER_POSITION control code [Display Devices], Video_IOCTLs_ebaaecc3-ace3-4252-8f01-d80bb1c2472f.xml, display.ioctl_video_query_pointer_position, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_POSITION
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
-	IOCTL_VIDEO_QUERY_POINTER_POSITION
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_POINTER_POSITION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns the current position of the pointer. Support for this modal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns a VIDEO_POINTER_POSITION structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the pointer position, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_POSITION); otherwise, the miniport driver sets this member to zero.


## -see-also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_POINTER_POSITION control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

