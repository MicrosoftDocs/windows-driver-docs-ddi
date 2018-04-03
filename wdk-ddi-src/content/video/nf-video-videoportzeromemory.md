---
UID: NF:video.VideoPortZeroMemory
title: VideoPortZeroMemory function
author: windows-driver-content
description: The VideoPortZeroMemory function fills a block of system memory with zeros.
old-location: display\videoportzeromemory.htm
old-project: display
ms.assetid: 96827d2e-0fee-4276-a758-82f5b7383eec
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortZeroMemory, VideoPortZeroMemory function [Display Devices], VideoPort_Functions_518c5fa4-2011-47bd-a24c-0dff144dfa3a.xml, display.videoportzeromemory, video/VideoPortZeroMemory
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortZeroMemory
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortZeroMemory function


## -description


The <b>VideoPortZeroMemory</b> function fills a block of system memory with zeros.


## -parameters




### -param Destination [out]

Specifies the starting address of the block of memory. This value must be in a mapped logical range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Length

Specifies the size, in bytes, of the block.


## -returns



None




## -remarks



Miniport drivers' <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> functions generally call <b>VideoPortZeroMemory</b> to initialize the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a> structure with zeros.

The given <i>Destination</i> must be in a mapped logical range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a> and/or a <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">system space</a> RAM address, such as an address on the stack. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570492">VideoPortZeroDeviceMemory</a> to fill any device-memory block, such as a <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a>, with zeros.

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroMemory</b>.

Callers of <b>VideoPortZeroMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570285">VideoPortCompareMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570332">VideoPortMoveMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570492">VideoPortZeroDeviceMemory</a>
 

 

