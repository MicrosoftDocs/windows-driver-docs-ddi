---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_POINTER
title: IOCTL_VIDEO_ENABLE_POINTER
author: windows-driver-content
description: Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an IOCTL_VIDEO_SET_POINTER_ATTR request before processing this request.
old-location: display\ioctl_video_enable_pointer.htm
old-project: display
ms.assetid: df6d348a-2720-4d47-9bc7-fc0627c951e6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_ENABLE_POINTER, IOCTL_VIDEO_ENABLE_POINTER control code [Display Devices], Video_IOCTLs_89a9a8cc-bfd6-4969-bb8f-26d72cbaa807.xml, display.ioctl_video_enable_pointer, ntddvdeo/IOCTL_VIDEO_ENABLE_POINTER
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
-	IOCTL_VIDEO_ENABLE_POINTER
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_ENABLE_POINTER IOCTL


## -description



Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568144">IOCTL_VIDEO_SET_POINTER_ATTR</a> request before processing this request.




## -ioctlparameters




### -input-buffer

None


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

The miniport driver does not set the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568144">IOCTL_VIDEO_SET_POINTER_ATTR</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_ENABLE_POINTER control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

