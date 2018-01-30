---
UID: NI:ntddvdeo.IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
title: IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
author: windows-driver-content
description: Releases a mapping between the virtual address space and the adapter's frame buffer and video RAM. Miniport drivers are required to support this nonmodal request.
old-location: display\ioctl_video_unmap_video_memory.htm
old-project: display
ms.assetid: 421cbe15-f2a6-495d-90f2-09a13771d018
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_unmap_video_memory, IOCTL_VIDEO_UNMAP_VIDEO_MEMORY control code [Display Devices], IOCTL_VIDEO_UNMAP_VIDEO_MEMORY, ntddvdeo/IOCTL_VIDEO_UNMAP_VIDEO_MEMORY, Video_IOCTLs_97fad6e5-d6e7-4487-84ab-cee66609ccd9.xml
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
-	IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_UNMAP_VIDEO_MEMORY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Releases a mapping between the virtual address space and the adapter's <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> and video RAM. Miniport drivers are required to support this nonmodal request.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a> structure, specifying the previously mapped virtual base address to be released with <a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>.


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

<a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_UNMAP_VIDEO_MEMORY control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

