---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
title: IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
author: windows-driver-content
description: Returns information about the adapter's &#0034;hardware cursor&#0034; features. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_capabilities.htm
old-project: display
ms.assetid: b282dcbe-f2ed-41f2-b97d-e9c409671197
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES, IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES control, IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES control code [Display Devices], Video_IOCTLs_42064dfd-73fb-4afc-aa3b-4e1ec4829e99.xml, display.ioctl_video_query_pointer_capabilities, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
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
-	IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_POINTER_CAPABILITIES IOCTL


## -description



Returns information about the adapter's "hardware cursor" features. Support for this modal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570525">VIDEO_POINTER_CAPABILITIES</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully returns the pointer capabilities, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_CAPABILITIES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570525">VIDEO_POINTER_CAPABILITIES</a>
 

 

