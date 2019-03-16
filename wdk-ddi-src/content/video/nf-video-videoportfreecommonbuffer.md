---
UID: NF:video.VideoPortFreeCommonBuffer
title: VideoPortFreeCommonBuffer function (video.h)
description: The VideoPortFreeCommonBuffer function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportfreecommonbuffer.htm
tech.root: display
ms.assetid: 8725868e-00bc-45fe-ab9d-c192abd1a059
ms.date: 05/10/2018
ms.keywords: VideoPortFreeCommonBuffer, VideoPortFreeCommonBuffer function [Display Devices], VideoPort_Functions_0f1acebf-0fdf-4152-ad91-2cafed40296c.xml, display.videoportfreecommonbuffer, video/VideoPortFreeCommonBuffer
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
- VideoPortFreeCommonBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortFreeCommonBuffer function


## -description


The <b>VideoPortFreeCommonBuffer</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570355">VideoPortReleaseCommonBuffer</a>.

<b>VideoPortFreeCommonBuffer</b> deallocates system memory that was allocated by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570308">VideoPortGetCommonBuffer</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Length [in]

Specifies the number of bytes of memory to be freed.


### -param VirtualAddress [in]

Pointer to the corresponding virtual address of the allocated memory range.


### -param LogicalAddress [in]

Specifies the logical address of the buffer to be freed.


### -param CacheEnabled [in]

Indicates whether the allocated memory is cached.


## -returns



None




## -remarks



Except for <a href="https://msdn.microsoft.com/c8329d26-fb6f-46f1-aacd-ba78ee4ea5d5">VideoPortGetCommonBuffer's </a><i>Alignment</i> parameter, all of the parameters used in a call to <b>VideoPortFreeCommonBuffer</b> must have the same values as those used in the previous call to <b>VideoPortGetCommonBuffer</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570308">VideoPortGetCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570355">VideoPortReleaseCommonBuffer</a>
 

 

