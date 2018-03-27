---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES
title: IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES
author: windows-driver-content
description: Returns the number of video modes supported by the adapter and the size in bytes of the video mode information, which can be used to allocate a buffer for an IOCTL_VIDEO_QUERY_AVAIL_MODES request.
old-location: display\ioctl_video_query_num_avail_modes.htm
old-project: display
ms.assetid: 7b12cbf2-7787-4e22-a554-2ce57d106347
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES, IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES control code [Display Devices], Video_IOCTLs_8396c439-2dc7-4def-98f9-f829417f7b0e.xml, display.ioctl_video_query_num_avail_modes, ntddvdeo/IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES
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
-	IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES IOCTL


## -description



Returns the number of video modes supported by the adapter and the size in bytes of the video mode information, which can be used to allocate a buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567816">IOCTL_VIDEO_QUERY_AVAIL_MODES</a> request. Miniport drivers are required to support this nonmodal request.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns the number of modes in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570523">VIDEO_NUM_MODES</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the mode count, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_NUM_MODES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567816">IOCTL_VIDEO_QUERY_AVAIL_MODES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570523">VIDEO_NUM_MODES</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

