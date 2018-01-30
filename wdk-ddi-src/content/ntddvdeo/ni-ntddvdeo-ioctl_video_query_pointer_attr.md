---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_ATTR
title: IOCTL_VIDEO_QUERY_POINTER_ATTR
author: windows-driver-content
description: Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_attr.htm
old-project: display
ms.assetid: 4c4a2742-977d-49b6-8644-a95f75365bc1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_query_pointer_attr, IOCTL_VIDEO_QUERY_POINTER_ATTR control code [Display Devices], IOCTL_VIDEO_QUERY_POINTER_ATTR, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_ATTR, Video_IOCTLs_2c99db8f-aa7f-4603-91f9-bdd7e17c62f7.xml
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
-	IOCTL_VIDEO_QUERY_POINTER_ATTR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_POINTER_ATTR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length


<text></text>



### -output-buffer

The miniport driver returns a VIDEO_POINTER_ATTRIBUTES structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length


<text></text>



### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the miniport driver successfully returns the pointer attributes, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_ATTRIBUTES); otherwise, the miniport driver sets this member to zero.


## -see-also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_POINTER_ATTR control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

