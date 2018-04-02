---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_CURRENT_MODE
title: IOCTL_VIDEO_QUERY_CURRENT_MODE
author: windows-driver-content
description: Returns information about the current adapter mode. Miniport drivers are required to support this modal request.
old-location: display\ioctl_video_query_current_mode.htm
old-project: display
ms.assetid: 16ce3db9-0295-4adc-9dc3-492b711adf2e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_VIDEO_QUERY_CURRENT_MODE, IOCTL_VIDEO_QUERY_CURRENT_MODE control code [Display Devices], Video_IOCTLs_18538d0f-5243-4326-850d-9fedf30e17cb.xml, display.ioctl_video_query_current_mode, ntddvdeo/IOCTL_VIDEO_QUERY_CURRENT_MODE
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
-	IOCTL_VIDEO_QUERY_CURRENT_MODE
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_CURRENT_MODE IOCTL


## -description



Returns information about the current adapter mode. Miniport drivers are required to support this modal request.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns the mode information in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570521">VIDEO_MODE_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the mode data, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_MODE_INFORMATION); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570521">VIDEO_MODE_INFORMATION</a>
 

 

