---
UID: NF:video.VideoPortWriteRegisterUshort
title: VideoPortWriteRegisterUshort function
author: windows-driver-content
description: The VideoPortWriteRegisterUshort function writes a USHORT value to a mapped register.
old-location: display\videoportwriteregisterushort.htm
old-project: display
ms.assetid: 0bc9b0a1-6cd8-4d76-a71e-694a8435773e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortWriteRegisterUshort, VideoPortWriteRegisterUshort function [Display Devices], VideoPort_Functions_b7adcb2e-bf7a-4ce3-bcd9-f11c24982b48.xml, display.videoportwriteregisterushort, video/VideoPortWriteRegisterUshort
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
-	VideoPortWriteRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortWriteRegisterUshort function


## -description


The <b>VideoPortWriteRegisterUshort</b> function writes a USHORT value to a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Value

Specifies a USHORT value to be transferred to the adapter.


## -returns



None




## -remarks



A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWriteRegisterUshort</b>.

Callers of <b>VideoPortWriteRegisterUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 

