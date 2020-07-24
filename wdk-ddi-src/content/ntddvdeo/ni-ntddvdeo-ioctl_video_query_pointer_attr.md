---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_ATTR
title: IOCTL_VIDEO_QUERY_POINTER_ATTR (ntddvdeo.h)
description: Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_attr.htm
tech.root: display
ms.assetid: 4c4a2742-977d-49b6-8644-a95f75365bc1
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_QUERY_POINTER_ATTR IOCTL"]
ms.keywords: IOCTL_VIDEO_QUERY_POINTER_ATTR, IOCTL_VIDEO_QUERY_POINTER_ATTR control, IOCTL_VIDEO_QUERY_POINTER_ATTR control code [Display Devices], Video_IOCTLs_2c99db8f-aa7f-4603-91f9-bdd7e17c62f7.xml, display.ioctl_video_query_pointer_attr, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_ATTR
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_ATTR"
 - "IOCTL_VIDEO_QUERY_POINTER_ATTR"
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
- IOCTL_VIDEO_QUERY_POINTER_ATTR
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_POINTER_ATTR IOCTL


## -description



Returns the attributes for the pointer, defined as a set of pixels used to paint the shape associated with the mouse. Support for this modal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a VIDEO_POINTER_ATTRIBUTES structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully returns the pointer attributes, it sets the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_ATTRIBUTES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>
 

 

