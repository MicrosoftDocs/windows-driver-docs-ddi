---
UID: NC:dispmprt.DXGKDDI_DPC_ROUTINE
title: DXGKDDI_DPC_ROUTINE
author: windows-driver-content
description: The DxgkDdiDpcRoutine function is called back at IRQL DISPATCH_LEVEL after the display miniport driver calls DxgkCbQueueDpc.
old-location: display\dxgkddidpcroutine.htm
old-project: display
ms.assetid: 2767906a-f084-4ccc-b24f-ba7d66c96477
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_DPC_ROUTINE, DmFunctions_12213354-74a5-40a5-a061-fa47d5a8cb03.xml, DxgkDdiDpcRoutine, DxgkDdiDpcRoutine callback function [Display Devices], display.dxgkddidpcroutine, dispmprt/DxgkDdiDpcRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
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
-	dispmprt.h
api_name:
-	DxgkDdiDpcRoutine
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_DPC_ROUTINE callback


## -description


The <i>DxgkDdiDpcRoutine</i> function is called back at IRQL DISPATCH_LEVEL after the display miniport driver calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>.


## -prototype


````
DXGKDDI_DPC_ROUTINE DxgkDdiDpcRoutine;

VOID DxgkDdiDpcRoutine(
  _In_ const PVOID MiniportDeviceContext
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


## -returns



None




## -remarks



Only one deferred procedure call (DPC) can be scheduled (at a given time) for a given display adapter.

If the display miniport driver is supporting several display adapters, the <i>DxgkDdiDpcRoutine</i> might be called in a reentrant fashion. That is, while <i>DxgkDdiDpcRoutine</i> is executing on one processor on behalf of a particular display adapter, it could be called again on another processor on behalf of a different display adapter.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>



 

 


