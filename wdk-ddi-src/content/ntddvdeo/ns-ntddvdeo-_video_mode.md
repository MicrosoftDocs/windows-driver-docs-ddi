---
UID: NS:ntddvdeo._VIDEO_MODE
title: "_VIDEO_MODE"
author: windows-driver-content
description: The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with IOCTL_VIDEO_SET_CURRENT_MODE.
old-location: display\video_mode.htm
old-project: display
ms.assetid: 01fad141-d023-4a3a-80ae-cb07985db8d1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVIDEO_MODE, PVIDEO_MODE, PVIDEO_MODE structure pointer [Display Devices], VIDEO_MODE, VIDEO_MODE structure [Display Devices], Video_Structs_7a64b36b-d8f2-411d-86e3-4fe854a94220.xml, _VIDEO_MODE, display.video_mode, ntddvdeo/PVIDEO_MODE, ntddvdeo/VIDEO_MODE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
api_name:
-	VIDEO_MODE
product: Windows
targetos: Windows
req.typenames: VIDEO_MODE, *PVIDEO_MODE
---

# _VIDEO_MODE structure


## -description


The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567846">IOCTL_VIDEO_SET_CURRENT_MODE</a>. 


## -struct-fields




### -field RequestedMode

Is the mode that the miniport driver should set if possible. In addition, the two high-order bits can be set to request special behavior from the miniport driver as follows:





#### VIDEO_MODE_ZERO_MEMORY

Indicates that the miniport driver should zero the video memory in conjunction with the mode set.



#### VIDEO_MODE_MAP_MEM_LINEAR

Indicates that the miniport driver should map the video memory in a linear fashion if the adapter supports such an operation.

