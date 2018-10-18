---
UID: NF:video.VideoPortReadRegisterBufferUlong
title: VideoPortReadRegisterBufferUlong function
author: windows-driver-content
description: The VideoPortReadRegisterBufferUlong function reads a number of ULONG values from a mapped device memory range and writes them into a buffer.
old-location: display\videoportreadregisterbufferulong.htm
tech.root: display
ms.assetid: ebef1d9f-9559-436c-b425-92ccf3bbf203
ms.date: 5/10/2018
ms.keywords: VideoPortReadRegisterBufferUlong, VideoPortReadRegisterBufferUlong function [Display Devices], VideoPort_Functions_69ff5729-b386-4527-8bca-adc70e2d467d.xml, display.videoportreadregisterbufferulong, video/VideoPortReadRegisterBufferUlong
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
-	VideoPortReadRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadRegisterBufferUlong function


## -description


The <b>VideoPortReadRegisterBufferUlong</b> function reads a number of ULONG values from a mapped device memory range and writes them into a buffer.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


### -param Buffer [out]

Pointer to a buffer into which the ULONG values are written.


### -param Count

Specifies the number of ULONG values to be written to the buffer.


## -returns



None




## -remarks



The buffer must be large enough to contain at least the specified number of ULONG values.

A miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterBufferUlong</b>.

Callers of <b>VideoPortReadRegisterBufferUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>
 

 

