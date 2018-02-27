---
UID: NF:video.VideoPortSynchronizeExecution
title: VideoPortSynchronizeExecution function
author: windows-driver-content
description: The VideoPortSynchronizeExecution function synchronizes the execution of a miniport driver-supplied HwVidSynchronizeExecutionCallback function with the miniport driver's HwVidInterrupt function, if any.
old-location: display\videoportsynchronizeexecution.htm
old-project: display
ms.assetid: 93c9e4f4-7b36-4815-b762-3ac528ac96ba
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortSynchronizeExecution, VideoPortSynchronizeExecution function [Display Devices], VideoPort_Functions_675225d0-5e49-4ad5-bdaa-f7341b9a96db.xml, display.videoportsynchronizeexecution, video/VideoPortSynchronizeExecution
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
req.irql: "<= DIRQL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortSynchronizeExecution
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortSynchronizeExecution function


## -description


The <b>VideoPortSynchronizeExecution</b> function synchronizes the execution of a miniport driver-supplied <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function with the miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> function, if any. Otherwise, it runs <i>HwVidSynchronizeExecutionCallback</i> at a raised priority.


## -syntax


````
BOOLEAN VideoPortSynchronizeExecution(
   PVOID                         HwDeviceExtension,
   VIDEO_SYNCHRONIZE_PRIORITY    Priority,
   PMINIPORT_SYNCHRONIZE_ROUTINE SynchronizeRoutine,
   PVOID                         Context
);
````


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
If <i>Priority</i> is set to <b>VpMediumPriority</b> and the miniport driver has an ISR associated with its video adapter, the call to the given <i>SynchronizeRoutine</i> is synchronized with the miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> function. Otherwise, synchronization is made at the <b>VpLowPriority</b> level.

</li>
<li>
<b>VpHighPriority</b> has the same effect as <b>VpMediumPriority</b>.

</li>
</ul>

### -param SynchronizeRoutine

Pointer to the miniport driver's <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function.


### -param Context

Pointer to a caller-supplied context to be passed to the miniport driver's <i>HwVidSynchronizeExecutionCallback</i> function. This pointer can be <b>NULL</b>.


## -returns



If the operation succeeds, <b>VideoPortSynchronizeExecution</b> returns <b>TRUE</b>.




## -remarks



Miniport drivers seldom call this routine unless either of the following conditions hold:

<ul>
<li>
The miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> function shares memory with other miniport driver functions. In order to access the shared memory in a multiprocessor-safe way, such miniport driver functions must call <b>VideoPortSynchronizeExecution</b> with <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>. This miniport driver function can safely access the shared memory because the video port driver prevents the <i>HwVidInterrupt</i> function from accessing the same memory concurrently.

</li>
<li>
The adapter must be programmed with a sequence of commands without being subject to a context switch. For example, a miniport driver's <i>SvgaHwIoPortXxx</i> function that has buffered a sequence of I/O instructions and validated the sequence might call <b>VideoPortSynchronizeExecution</b> with <i>HwVidSynchronizeExecutionCallback</i>. This miniport driver function can transfer the buffered and validated I/O stream to the adapter very quickly.

</li>
</ul>
A caller should specify the lowest practical <i>Priority</i> value for the work <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> must do. Any <i>CallbackRoutine</i> that is run at a high hardware priority (<b>VpMediumPriority</b> or <b>VpHighPriority</b>) should return control as quickly as possible. A driver with such a high-priority <i>HwVidSynchronizeExecutionCallback</i> function should be designed to do as much work as possible in every other driver function except one of both of its <i>HwVidSynchronizeExecutionCallback</i> and <i>HwVidInterrupt</i> functions.

Callers of <b>VideoPortSynchronizeExecution</b> must be running at IRQL 




## -see-also

<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSynchronizeExecution function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

