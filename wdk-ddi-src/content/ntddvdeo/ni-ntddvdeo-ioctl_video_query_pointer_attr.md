---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_ATTR
title: IOCTL_VIDEO_QUERY_POINTER_ATTR
author: windows-driver-content
description: Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_attr.htm
old-project: display
ms.assetid: 4c4a2742-977d-49b6-8644-a95f75365bc1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_QUERY_POINTER_ATTR, IOCTL_VIDEO_QUERY_POINTER_ATTR control code [Display Devices], Video_IOCTLs_2c99db8f-aa7f-4603-91f9-bdd7e17c62f7.xml, display.ioctl_video_query_pointer_attr, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_ATTR
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
-	IOCTL_VIDEO_QUERY_POINTER_ATTR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_POINTER_ATTR IOCTL


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



 

 


