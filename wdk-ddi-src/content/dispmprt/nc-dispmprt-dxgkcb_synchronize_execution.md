---
UID: NC:dispmprt.DXGKCB_SYNCHRONIZE_EXECUTION
title: DXGKCB_SYNCHRONIZE_EXECUTION (dispmprt.h)
description: The DxgkCbSynchronizeExecution function synchronizes a specified function, implemented by the display miniport driver, with the display miniport driver's DxgkDdiInterruptRoutine function.
old-location: display\dxgkcbsynchronizeexecution.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKCB_SYNCHRONIZE_EXECUTION callback function"]
ms.keywords: DXGKCB_SYNCHRONIZE_EXECUTION, DXGKCB_SYNCHRONIZE_EXECUTION callback, DpFunctions_3d9aecd7-8082-4869-a0d1-4a6cdadc4839.xml, DxgkCbSynchronizeExecution, DxgkCbSynchronizeExecution callback function [Display Devices], display.dxgkcbsynchronizeexecution, dispmprt/DxgkCbSynchronizeExecution
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_SYNCHRONIZE_EXECUTION
 - dispmprt/DXGKCB_SYNCHRONIZE_EXECUTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_SYNCHRONIZE_EXECUTION
---

# DXGKCB_SYNCHRONIZE_EXECUTION callback function


## -description

The <b>DxgkCbSynchronizeExecution</b> function synchronizes a specified function, implemented by the display miniport driver, with the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a> function.

## -parameters

### -param DeviceHandle 

[in]
A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.

### -param SynchronizeRoutine 

[in]
A pointer to a function, implemented by the display miniport driver, that will be synchronized with <i>DxgkDdiInterruptRoutine</i>. The function must conform to the following prototype:

```cpp
BOOLEAN SynchronizeRoutine(PVOID Context);
```

### -param Context 

[in]
A pointer to a context block, created by the display miniport driver, that will be passed to <i>SynchronizeRoutine</i>.

### -param MessageNumber 

[in]
The number of the interrupt message with which <i>SynchronizeRoutine</i> will be synchronized. If the interrupt is line-based, this parameter must be zero.

### -param ReturnValue 

[out]
A pointer to a Boolean variable that receives the return value of <i>SynchronizeRoutine</i>.

## -returns

<b>DxgkCbSynchronizeExecution</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|One of the parameters is invalid.|
|STATUS_UNSUCCESSFUL|The function was unable to synchronize execution, possibly because the interrupt had not been connected yet.|

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a>

