---
UID: NC:d3dkmddi.DXGKDDI_CANCELCOMMAND
title: DXGKDDI_CANCELCOMMAND
author: windows-driver-content
description: Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but never reached the hardware queue because the device went into an error state.
old-location: display\dxgkddicancelcommand.htm
old-project: display
ms.assetid: c290c313-14ee-4554-9bb1-8adec1892426
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgkddicancelcommand, DxgkDdiCancelCommand callback function [Display Devices], DxgkDdiCancelCommand, DXGKDDI_CANCELCOMMAND, DXGKDDI_CANCELCOMMAND, d3dkmddi/DxgkDdiCancelCommand
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dkmddi.h
apiname:
-	DxgkDdiCancelCommand
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CANCELCOMMAND callback


## -description


Cleans up internal resources associated with a direct memory access (DMA) packet that was in the GPU scheduler's software queue but  never reached the hardware queue because the device went into an error state. Such an error state is typically caused by a <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> event.


## -prototype


````
DXGKDDI_CANCELCOMMAND DxgkDdiCancelCommand;

_Check_return_ NTSTATUS APIENTRY* DxgkDdiCancelCommand(
  _In_ const HANDLE                hAdapter,
  _In_ const DXGKARG_CANCELCOMMAND *pCancelCommand
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCancelCommand [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_cancelcommand.md">DXGKARG_CANCELCOMMAND</a> structure that specifies resources to be cleaned up after a command is removed from the hardware  queue.


## -returns



Returns <b>STATUS_SUCCESS</b> upon successful completion. If the driver instead returns an error code, the operating system causes a system bugcheck to occur. For more information, see the following Remarks section.




## -remarks



<div class="alert"><b>Note</b>  The DirectX graphics kernel subsystem calls this function only if the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md">DXGK_VIDSCHCAPS</a>.<b>CancelCommandAware</b> member is set.</div>
<div> </div>
If the driver returns an error code, the DirectX graphics kernel subsystem  causes a system bugcheck to occur. In a crash dump file, the error is noted by the message <b>BugCheck 0x119</b>, which has the following four parameters.

<ol>
<li>0x9</li>
<li>The NTSTATUS error code returned from the failed driver call</li>
<li>A pointer to the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_cancelcommand.md">DXGKARG_CANCELCOMMAND</a> structure</li>
<li>A pointer to an internal scheduler data structure</li>
</ol>



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_cancelcommand.md">DXGKARG_CANCELCOMMAND</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md">DXGK_VIDSCHCAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CANCELCOMMAND callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

