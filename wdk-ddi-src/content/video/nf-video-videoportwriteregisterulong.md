---
UID: NF:video.VideoPortWriteRegisterUlong
title: VideoPortWriteRegisterUlong function
author: windows-driver-content
description: The VideoPortWriteRegisterUlong function writes a ULONG value to a mapped register.
old-location: display\videoportwriteregisterulong.htm
old-project: display
ms.assetid: 6d7b5e2f-a7c3-46ee-a03a-f80f8e1ada07
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortWriteRegisterUlong, VideoPortWriteRegisterUlong function [Display Devices], VideoPort_Functions_18ff4439-1c87-44fe-b695-3903b0093e55.xml, display.videoportwriteregisterulong, video/VideoPortWriteRegisterUlong
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
-	VideoPortWriteRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterUlong function


## -description


The <b>VideoPortWriteRegisterUlong</b> function writes a ULONG value to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a ULONG value to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUlong</b>.

Callers of <b>VideoPortWriteRegisterUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 

