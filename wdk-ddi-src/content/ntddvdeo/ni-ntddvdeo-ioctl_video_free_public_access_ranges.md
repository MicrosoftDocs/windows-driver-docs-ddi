---
UID: NI:ntddvdeo.IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
title: IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
author: windows-driver-content
description: Releases the address range that was allocated by a preceding IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES request. Support for this nonmodal request is optional.
old-location: display\ioctl_video_free_public_access_ranges.htm
old-project: display
ms.assetid: 6adc5234-a7c3-4860-8d3e-6c990f460ecc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
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
req.alt-api: IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES
req.alt-loc: Ntddvdeo.h
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
req.typenames: *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
---

# IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES IOCTL



## -description

Releases the address range that was allocated by a preceding <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_public_access_ranges.md">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a> request. Support for this nonmodal request is optional.



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
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_public_access_ranges.md">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a>
</dt>
<dt>
<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_FREE_PUBLIC_ACCESS_RANGES control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

