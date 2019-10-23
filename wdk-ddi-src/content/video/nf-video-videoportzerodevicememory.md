---
UID: NF:video.VideoPortZeroDeviceMemory
title: VideoPortZeroDeviceMemory function (video.h)
description: The VideoPortZeroDeviceMemory function fills an adapter frame buffer or other device memory with zeros.
old-location: display\videoportzerodevicememory.htm
tech.root: display
ms.assetid: 1f59ae13-022b-426c-9eef-9a8e5f5a85f2
ms.date: 05/10/2018
ms.keywords: VideoPortZeroDeviceMemory, VideoPortZeroDeviceMemory function [Display Devices], VideoPort_Functions_42829075-dd6d-49fd-a4d6-3ee19152335d.xml, display.videoportzerodevicememory, video/VideoPortZeroDeviceMemory
ms.topic: function
f1_keywords:
 - "video/VideoPortZeroDeviceMemory"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortZeroDeviceMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortZeroDeviceMemory function


## -description


The <b>VideoPortZeroDeviceMemory</b> function fills an adapter <a href="https://docs.microsoft.com/windows-hardware/drivers/">frame buffer</a> or other device memory with zeros.


## -parameters




### -param Destination [out]

Specifies the base address of the adapter memory area. This value must be a mapped logical address returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


### -param Length

Specifies the size, in bytes, to be filled.


## -returns



None




## -remarks



Miniport drivers should <i>always</i> call this function, rather than <b>VideoPortZeroMemory</b>, to fill on-adapter memory with zeros.

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroDeviceMemory</b>.

Callers of <b>VideoPortZeroDeviceMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzeromemory">VideoPortZeroMemory</a>
 

 

