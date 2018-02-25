---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
title: IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
author: windows-driver-content
description: Returns an array, possibly with one element, of address ranges used to program the adapter registers or ports directly. Support for this nonmodal request is optional.
old-location: display\ioctl_video_query_public_access_ranges.htm
old-project: display
ms.assetid: 2ae79e9c-34e4-4862-afd1-be6e808183cf
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES, IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES control code [Display Devices], Video_IOCTLs_e41d01a5-e889-445e-87cd-948f95ba2810.xml, display.ioctl_video_query_public_access_ranges, ntddvdeo/IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
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
-	IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns an array, possibly with one element, of address ranges used to program the adapter registers or ports directly. Support for this nonmodal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns an array of <a href="..\ntddvdeo\ns-ntddvdeo-_video_public_access_ranges.md">VIDEO_PUBLIC_ACCESS_RANGES</a> in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver returns an address range or ranges, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_PUBLIC_ACCESS_RANGES); otherwise, the miniport driver sets this member to zero.


## -see-also

<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>



<a href="..\ntddvdeo\ns-ntddvdeo-_video_public_access_ranges.md">VIDEO_PUBLIC_ACCESS_RANGES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

