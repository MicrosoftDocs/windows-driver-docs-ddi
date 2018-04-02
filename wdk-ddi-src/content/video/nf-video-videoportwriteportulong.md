---
UID: NF:video.VideoPortWritePortUlong
title: VideoPortWritePortUlong function
author: windows-driver-content
description: The VideoPortWritePortUlong function writes a ULONG value to a mapped I/O port.
old-location: display\videoportwriteportulong.htm
old-project: display
ms.assetid: 395e4a37-ea14-4dc0-926d-2b2336aa5221
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortWritePortUlong, VideoPortWritePortUlong function [Display Devices], VideoPort_Functions_83cb0bbd-0dba-4cd6-b9f5-b8b0091371cd.xml, display.videoportwriteportulong, video/VideoPortWritePortUlong
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortWritePortUlong
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortWritePortUlong function


## -description


The <b>VideoPortWritePortUlong</b> function writes a ULONG value to a mapped I/O port.


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a ULONG value to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortUlong</b>.

Callers of <b>VideoPortWritePortUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 

