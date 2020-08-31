---
UID: NF:video.VideoPortZeroMemory
title: VideoPortZeroMemory function (video.h)
description: The VideoPortZeroMemory function fills a block of system memory with zeros.
old-location: display\videoportzeromemory.htm
tech.root: display
ms.assetid: 96827d2e-0fee-4276-a758-82f5b7383eec
ms.date: 05/10/2018
keywords: ["VideoPortZeroMemory function"]
ms.keywords: VideoPortZeroMemory, VideoPortZeroMemory function [Display Devices], VideoPort_Functions_518c5fa4-2011-47bd-a24c-0dff144dfa3a.xml, display.videoportzeromemory, video/VideoPortZeroMemory
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortZeroMemory
 - video/VideoPortZeroMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortZeroMemory
---

# VideoPortZeroMemory function


## -description

The <b>VideoPortZeroMemory</b> function fills a block of system memory with zeros.

## -parameters

### -param Destination 

[out]
Specifies the starting address of the block of memory. This value must be in a mapped logical range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Length

Specifies the size, in bytes, of the block.

## -returns

None

## -remarks

Miniport drivers' <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> functions generally call <b>VideoPortZeroMemory</b> to initialize the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure with zeros.

The given <i>Destination</i> must be in a mapped logical range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a> and/or a <a href="https://docs.microsoft.com/windows-hardware/drivers/">system space</a> RAM address, such as an address on the stack. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzerodevicememory">VideoPortZeroDeviceMemory</a> to fill any device-memory block, such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/">frame buffer</a>, with zeros.

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroMemory</b>.

Callers of <b>VideoPortZeroMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL < DISPATCH_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcomparememory">VideoPortCompareMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmovememory">VideoPortMoveMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzerodevicememory">VideoPortZeroDeviceMemory</a>

