---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
title: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
author: windows-driver-content
description: Returns the color-capabilities information found in the VDDP description file for the adapter.
old-location: display\ioctl_video_query_color_capabilities.htm
old-project: display
ms.assetid: ba1a1fcd-9551-41cb-b1f9-097b51a26380
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES, IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES control, IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES control code [Display Devices], Video_IOCTLs_26b0d5c4-d7b5-4056-9d78-6b9fa9a8ab72.xml, display.ioctl_video_query_color_capabilities, ntddvdeo/IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
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
-	IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES IOCTL


## -description



Returns the color-capabilities information found in the VDDP description file for the adapter. Support for this nonmodal request is optional. However, if a miniport driver supports this request, it cannot return a subset of the color-capabilities information.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns all VIDEO_COLOR_CAPABILITIES information in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the color-capabilities data, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_COLOR_CAPABILITIES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

