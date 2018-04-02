---
UID: NF:video.VideoPortReadRegisterUshort
title: VideoPortReadRegisterUshort function
author: windows-driver-content
description: The VideoPortReadRegisterUshort function reads a USHORT value from a mapped register range.
old-location: display\videoportreadregisterushort.htm
old-project: display
ms.assetid: fdf5d153-74ca-437e-82ab-b85c89dc9fd1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortReadRegisterUshort, VideoPortReadRegisterUshort function [Display Devices], VideoPort_Functions_c6ee8be3-3b15-4f22-8008-63d132ec7379.xml, display.videoportreadregisterushort, video/VideoPortReadRegisterUshort
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
-	VideoPortReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReadRegisterUshort function


## -description


The <b>VideoPortReadRegisterUshort</b> function reads a USHORT value from a mapped register range.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadRegisterUshort</b> returns the USHORT value read from the adapter.




## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterUshort</b>.

Callers of <b>VideoPortReadRegisterUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 

