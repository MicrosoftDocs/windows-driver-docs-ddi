---
UID: NI:ntddvdeo.IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
title: IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
author: windows-driver-content
description: Releases the address range that was allocated by a preceding IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES request. Support for this nonmodal request is optional.
old-location: display\ioctl_video_free_public_access_ranges.htm
old-project: display
ms.assetid: 6adc5234-a7c3-4860-8d3e-6c990f460ecc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES, IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES control code [Display Devices], Video_IOCTLs_8b60ca4e-5d15-4fa1-8257-805d90276262.xml, display.ioctl_video_free_public_access_ranges, ntddvdeo/IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
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
-	IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES IOCTL


## -description



Releases the address range that was allocated by a preceding <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_public_access_ranges.md">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a> request. Support for this nonmodal request is optional.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains an array of <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a> structures to be released.


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

<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_public_access_ranges.md">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a>



 

 


