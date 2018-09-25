---
UID: NC:d3dkmddi.DXGKDDI_PREEMPTCOMMAND
title: DXGKDDI_PREEMPTCOMMAND
author: windows-driver-content
description: The DxgkDdiPreemptCommand function preempts a direct memory access (DMA) buffer that was previously submitted to and currently queued in the hardware command execution unit.
old-location: display\dxgkddipreemptcommand.htm
ms.assetid: 8cea02d4-f25e-4ff4-8c9e-aa360a764c4b
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_PREEMPTCOMMAND, DXGKDDI_PREEMPTCOMMAND callback, DmFunctions_a378e47e-622c-41bf-95e7-21e4088d7026.xml, DxgkDdiPreemptCommand, DxgkDdiPreemptCommand callback function [Display Devices], d3dkmddi/DxgkDdiPreemptCommand, display.dxgkddipreemptcommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiPreemptCommand
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_PREEMPTCOMMAND callback function


## -description


The <i>DxgkDdiPreemptCommand</i> function preempts a direct memory access (DMA) buffer that was previously submitted to and currently queued in the hardware command execution unit.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pPreemptCommand [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557616">DXGKARG_PREEMPTCOMMAND</a> structure that describes the command that is used to preempt a DMA buffer previously submitted to the hardware command execution unit.


## -returns




      Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.




## -remarks



If the driver determines that the hardware is already finished processing all of the submitted DMA buffers--and that the hardware informed the graphics processing unit (GPU) scheduler about the completions--when its <i>DxgkDdiPreemptCommand</i> function is called to preempt the DMA buffers, the driver should perform the following operations instead of submitting the preempt fence that is identified by the <b>PreemptionFenceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff557616">DXGKARG_PREEMPTCOMMAND</a> to the hardware:

<ul>
<li>
Raise IRQL to interrupt level. For example, the driver can call the <a href="https://msdn.microsoft.com/9c659319-d0a5-43a7-b9a9-9fad18397a09">DxgkCbSynchronizeExecution</a> function to synchronize with its <a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a> function.

</li>
<li>
Inform the GPU scheduler about the preemption information. The driver can either call the <a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a> function directly or call its <a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a> function (for example, if the driver must perform other updates as well).

Note that the GPU scheduler handles instances where the hardware has stopped responding because of Timeout Detection and Recovery (TDR) work.

</li>
</ul>
If the driver returns an error code, the Microsoft DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x2</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557616">DXGKARG_PREEMPTCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>
<i>DxgkDdiPreemptCommand</i> should be made nonpageable because it runs at IRQL = DISPATCH_LEVEL




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557616">DXGKARG_PREEMPTCOMMAND</a>



<a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a>



<a href="https://msdn.microsoft.com/9c659319-d0a5-43a7-b9a9-9fad18397a09">DxgkCbSynchronizeExecution</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a>
 

 

