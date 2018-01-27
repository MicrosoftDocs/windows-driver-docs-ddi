---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_POINTER_ATTR
title: IOCTL_VIDEO_SET_POINTER_ATTR
author: windows-driver-content
description: Sets the pointer attributes.
old-location: display\ioctl_video_set_pointer_attr.htm
old-project: display
ms.assetid: fa83c6b4-a1e5-49b7-9264-0b2f20748b4b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_set_pointer_attr, IOCTL_VIDEO_SET_POINTER_ATTR control code [Display Devices], IOCTL_VIDEO_SET_POINTER_ATTR, ntddvdeo/IOCTL_VIDEO_SET_POINTER_ATTR, Video_IOCTLs_78cd33bc-5c7d-4b6c-bfac-64e0cc33e475.xml
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
-	IOCTL_VIDEO_SET_POINTER_ATTR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_POINTER_ATTR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Sets the pointer attributes. Support for this modal request is optional. A supporting miniport driver can fail this request (for example, if the attributes specify a larger pointer than the miniport driver can supply). When a miniport driver fails this request, the corresponding display driver must manage the pointer.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_POINTER_ATTRIBUTES structure to be set.


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

