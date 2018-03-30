---
UID: NC:d3dkmddi.DXGKDDI_CANCELCOMMAND
title: DXGKDDI_CANCELCOMMAND
author: windows-driver-content
description: Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but never reached the hardware queue because the device went into an error state.
old-location: display\dxgkddicancelcommand.htm
old-project: display
ms.assetid: c290c313-14ee-4554-9bb1-8adec1892426
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_CANCELCOMMAND, DxgkDdiCancelCommand, DxgkDdiCancelCommand callback function [Display Devices], d3dkmddi/DxgkDdiCancelCommand, display.dxgkddicancelcommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiCancelCommand
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CANCELCOMMAND callback


## -description


Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but  never reached the hardware queue because the device went into an error state. Such an error state is typically caused by a <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> event.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pCancelCommand [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451250">DXGKARG_CANCELCOMMAND</a> structure that specifies resources to be cleaned up after a command is removed from the hardware  queue.


## -returns



Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.




## -remarks



<div class="alert"><b>Note</b>  The DirectX graphics kernel subsystem calls this function only if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562863">DXGK_VIDSCHCAPS</a>.<b>CancelCommandAware</b> member is set.</div>
<div> </div>
If the driver returns an error code, the DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x9</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451250">DXGKARG_CANCELCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451250">DXGKARG_CANCELCOMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562863">DXGK_VIDSCHCAPS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

