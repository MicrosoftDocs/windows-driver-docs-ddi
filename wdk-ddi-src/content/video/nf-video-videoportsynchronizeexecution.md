---
UID: NF:video.VideoPortSynchronizeExecution
title: VideoPortSynchronizeExecution function
description: The VideoPortSynchronizeExecution function synchronizes the execution of a miniport driver-supplied HwVidSynchronizeExecutionCallback function with the miniport driver's HwVidInterrupt function, if any.
old-location: display\videoportsynchronizeexecution.htm
tech.root: display
ms.assetid: 93c9e4f4-7b36-4815-b762-3ac528ac96ba
ms.date: 05/10/2018
ms.keywords: VideoPortSynchronizeExecution, VideoPortSynchronizeExecution function [Display Devices], VideoPort_Functions_675225d0-5e49-4ad5-bdaa-f7341b9a96db.xml, display.videoportsynchronizeexecution, video/VideoPortSynchronizeExecution
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
req.irql: "<= DIRQL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortSynchronizeExecution
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortSynchronizeExecution function


## -description


The <b>VideoPortSynchronizeExecution</b> function synchronizes the execution of a miniport driver-supplied <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function with the miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function, if any. Otherwise, it runs <i>HwVidSynchronizeExecutionCallback</i> at a raised priority.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param Priority

Specifies the type of priority at which the given <i>SynchronizeRoutine</i> must be run, as one of the following:

<ul>
<li>
If <i>Priority</i> is set to <b>VpLowPriority</b>, the current thread is raised to the highest noninterrupt-masking priority. Accordingly, the current thread can be preempted only by an ISR if a device interrupts.

</li>
<li>
If <i>Priority</i> is set to <b>VpMediumPriority</b> and the miniport driver has an ISR associated with its video adapter, the call to the given <i>SynchronizeRoutine</i> is synchronized with the miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function. Otherwise, synchronization is made at the <b>VpLowPriority</b> level.

</li>
<li>
<b>VpHighPriority</b> has the same effect as <b>VpMediumPriority</b>.

</li>
</ul>

### -param SynchronizeRoutine

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function.


### -param Context

Pointer to a caller-supplied context to be passed to the miniport driver's <i>HwVidSynchronizeExecutionCallback</i> function. This pointer can be <b>NULL</b>.


## -returns



If the operation succeeds, <b>VideoPortSynchronizeExecution</b> returns <b>TRUE</b>.




## -remarks



Miniport drivers seldom call this routine unless either of the following conditions hold:

<ul>
<li>
The miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> function shares memory with other miniport driver functions. In order to access the shared memory in a multiprocessor-safe way, such miniport driver functions must call <b>VideoPortSynchronizeExecution</b> with <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>. This miniport driver function can safely access the shared memory because the video port driver prevents the <i>HwVidInterrupt</i> function from accessing the same memory concurrently.

</li>
<li>
The adapter must be programmed with a sequence of commands without being subject to a context switch. For example, a miniport driver's <i>SvgaHwIoPortXxx</i> function that has buffered a sequence of I/O instructions and validated the sequence might call <b>VideoPortSynchronizeExecution</b> with <i>HwVidSynchronizeExecutionCallback</i>. This miniport driver function can transfer the buffered and validated I/O stream to the adapter very quickly.

</li>
</ul>
A caller should specify the lowest practical <i>Priority</i> value for the work <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> must do. Any <i>CallbackRoutine</i> that is run at a high hardware priority (<b>VpMediumPriority</b> or <b>VpHighPriority</b>) should return control as quickly as possible. A driver with such a high-priority <i>HwVidSynchronizeExecutionCallback</i> function should be designed to do as much work as possible in every other driver function except one of both of its <i>HwVidSynchronizeExecutionCallback</i> and <i>HwVidInterrupt</i> functions.

Callers of <b>VideoPortSynchronizeExecution</b> must be running at IRQL 




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>
 

 

