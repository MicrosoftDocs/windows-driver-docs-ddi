---
UID: NC:video.PMINIPORT_SYNCHRONIZE_ROUTINE
title: PMINIPORT_SYNCHRONIZE_ROUTINE
description: HwVidSynchronizeExecutionCallback is an optional miniport driver function, passed in calls to VideoPortSynchronizeExecution.
old-location: display\hwvidsynchronizeexecutioncallback.htm
tech.root: display
ms.assetid: 04e3bac6-c905-4c95-bd1b-e85b46c4296d
ms.date: 05/10/2018
ms.keywords: HwVidSynchronizeExecutionCallback, HwVidSynchronizeExecutionCallback callback function [Display Devices], PMINIPORT_SYNCHRONIZE_ROUTINE, PMINIPORT_SYNCHRONIZE_ROUTINE callback, VideoMiniport_Functions_98ebe64f-4ba9-475b-8095-b97dceaaf946.xml, display.hwvidsynchronizeexecutioncallback, video/HwVidSynchronizeExecutionCallback
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidSynchronizeExecutionCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMINIPORT_SYNCHRONIZE_ROUTINE callback function


## -description


<i>HwVidSynchronizeExecutionCallback</i> is an optional miniport driver function, passed in calls to <b>VideoPortSynchronizeExecution</b>.


## -parameters




### -param Context

Pointer to context data passed to the callback routine through <b>VideoPortSynchronizeExecution</b>. Usually, this is a pointer to the device extension or an offset within the device extension.


## -returns



If the operation succeeds, <i>HwVidSynchronizeExecutionCallback</i> returns <b>TRUE</b>.




## -remarks



A miniport driver with one or more functions that share memory with its <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function must have a <i>HwVidSynchronizeExecutionCallback</i> function. Any function that shares memory with <i>HwVidInterrupt</i> must call <b>VideoPortSynchronizeExecution</b> with the <i>HwVidSynchronizeExecutionCallback</i> function to maintain the integrity of data in the shared memory area. That is, only one of the <i>HwVidSynchronizeExecutionCallback</i> and <i>HwVidInterrupt</i> functions can update state in the shared area at any given moment.

The miniport driver of an adapter that does not generate interrupts also can have an <i>HwVidSynchronizeExecutionCallback</i> function to be passed to <b>VideoPortSynchronizeExecution</b> when such a driver needs to get some critical work done at a relatively high run-time priority. For example, VGA-compatible miniport drivers with <i>SvgaHwIoPortXxx</i> functions (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>) might have a <i>HwVidSynchronizeExecutionCallback</i> function that is responsible for transferring driver-buffered and validated application-issued I/O to the adapter.

<i>HwVidSynchronizeExecutionCallback</i> must not be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>
 

 

