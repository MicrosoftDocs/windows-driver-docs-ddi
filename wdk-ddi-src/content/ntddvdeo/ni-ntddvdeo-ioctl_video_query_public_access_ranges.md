---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
title: IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
author: windows-driver-content
description: Returns an array, possibly with one element, of address ranges used to program the adapter registers or ports directly. Support for this nonmodal request is optional.
old-location: display\ioctl_video_query_public_access_ranges.htm
tech.root: display
ms.assetid: 2ae79e9c-34e4-4862-afd1-be6e808183cf
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES, IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES control, IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES control code [Display Devices], Video_IOCTLs_e41d01a5-e889-445e-87cd-948f95ba2810.xml, display.ioctl_video_query_public_access_ranges, ntddvdeo/IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
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
-	IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES IOCTL


## -description



Returns an array, possibly with one element, of address ranges used to program the adapter registers or ports directly. Support for this nonmodal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff570546">VIDEO_PUBLIC_ACCESS_RANGES</a> in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver returns an address range or ranges, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_PUBLIC_ACCESS_RANGES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570546">VIDEO_PUBLIC_ACCESS_RANGES</a>
 

 

