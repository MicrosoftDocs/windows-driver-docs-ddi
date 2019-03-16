---
UID: NC:d3dkmddi.DXGKDDI_RESETENGINE
title: DXGKDDI_RESETENGINE (d3dkmddi.h)
description: The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.
old-location: display\dxgkddiresetengine.htm
ms.assetid: 9c2097b2-5742-422c-a650-7efff2484970
ms.date: 05/10/2018
ms.keywords: DXGKDDI_RESETENGINE, DXGKDDI_RESETENGINE callback, DxgkDdiResetEngine, DxgkDdiResetEngine callback function [Display Devices], d3dkmddi/DxgkDdiResetEngine, display.dxgkddiresetengine
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmddi.h
api_name:
- DxgkDdiResetEngine
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_RESETENGINE callback function


## -description


The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pResetEngine [in, out]

A value of type  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451303">DXGKARG_RESETENGINE</a> that specifies nodes that are to be reset and supplies a fence identifier for the last aborted packet.


## -returns



Returns <b>STATUS_SUCCESS</b> if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.




## -remarks



The display miniport driver should return from a call to this function only when the reset operation is completed, nothing remains in the physical adapter's hardware queue, and the specified nodes are ready to accept new packets.

 This function should be made pageable.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://msdn.microsoft.com/9fce6a18-2a66-4518-b05b-e85bdaa3951f">Threading and Synchronization First Level</a>.

For more information, see  <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451303">DXGKARG_RESETENGINE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

