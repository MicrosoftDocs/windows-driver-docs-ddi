---
UID: NF:video.VideoPortZeroDeviceMemory
title: VideoPortZeroDeviceMemory function
author: windows-driver-content
description: The VideoPortZeroDeviceMemory function fills an adapter frame buffer or other device memory with zeros.
old-location: display\videoportzerodevicememory.htm
old-project: display
ms.assetid: 1f59ae13-022b-426c-9eef-9a8e5f5a85f2
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortZeroDeviceMemory, VideoPortZeroDeviceMemory function [Display Devices], VideoPort_Functions_42829075-dd6d-49fd-a4d6-3ee19152335d.xml, display.videoportzerodevicememory, video/VideoPortZeroDeviceMemory
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
-	VideoPortZeroDeviceMemory
product: Windows
targetos: Windows
req.typenames: 
---

# VideoPortZeroDeviceMemory function


## -description


The <b>VideoPortZeroDeviceMemory</b> function fills an adapter <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> or other device memory with zeros.


## -parameters




### -param Destination [out]

Specifies the base address of the adapter memory area. This value must be a mapped logical address returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Length

Specifies the size, in bytes, to be filled.


## -returns



None




## -remarks



Miniport drivers should <i>always</i> call this function, rather than <b>VideoPortZeroMemory</b>, to fill on-adapter memory with zeros.

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortZeroDeviceMemory</b>.

Callers of <b>VideoPortZeroDeviceMemory</b> can be running at any IRQL if the memory pointed to by the <i>Destination</i> parameter is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570493">VideoPortZeroMemory</a>
 

 

