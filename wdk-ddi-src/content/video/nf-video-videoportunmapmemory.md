---
UID: NF:video.VideoPortUnmapMemory
title: VideoPortUnmapMemory function (video.h)
description: The VideoPortUnmapMemory function releases a mapping between a logical address range for the adapter and a virtual address range in the user-mode address space of a particular thread. This function is the complement of VideoPortMapMemory.
old-location: display\videoportunmapmemory.htm
tech.root: display
ms.assetid: 224c8483-56b8-4341-8347-fa119ec04024
ms.date: 05/10/2018
ms.keywords: VideoPortUnmapMemory, VideoPortUnmapMemory function [Display Devices], VideoPort_Functions_394a66fa-47cd-4e0e-8467-3c3562d27822.xml, display.videoportunmapmemory, video/VideoPortUnmapMemory
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortUnmapMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortUnmapMemory function


## -description


The <b>VideoPortUnmapMemory</b> function releases a mapping between a logical address range for the adapter and a virtual address range in the user-mode address space of a particular thread. This function is the complement of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportmapmemory">VideoPortMapMemory</a>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param VirtualAddress

Pointer to a virtual address within the mapped range to be released.


### -param ProcessHandle

Should be set to zero, or to the process handle specified when the miniport driver called <b>VideoPortMapMemory</b>.


## -returns



<b>VideoPortUnmapMemory</b> returns NO_ERROR if the mapping was released. Otherwise, it returns ERROR_INVALID_PARAMETER.




## -remarks



A miniport driver cannot release a subrange of the mapping between a logical device range and the user-space virtual address range of its corresponding display driver. Whether the <i>VirtualAddress</i> parameter is the base virtual address for the mapped range that was returned by <b>VideoPortMapMemory</b>, or is an offset into that mapped virtual range, <b>VideoPortUnmapMemory</b> releases the mapping for the full range. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportmapmemory">VideoPortMapMemory</a>
 

 

