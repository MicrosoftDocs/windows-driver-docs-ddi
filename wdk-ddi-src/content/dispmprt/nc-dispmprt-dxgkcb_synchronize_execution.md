---
UID: NC:dispmprt.DXGKCB_SYNCHRONIZE_EXECUTION
title: DXGKCB_SYNCHRONIZE_EXECUTION
author: windows-driver-content
description: The DxgkCbSynchronizeExecution function synchronizes a specified function, implemented by the display miniport driver, with the display miniport driver's DxgkDdiInterruptRoutine function.
old-location: display\dxgkcbsynchronizeexecution.htm
old-project: display
ms.assetid: 9c659319-d0a5-43a7-b9a9-9fad18397a09
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKCB_SYNCHRONIZE_EXECUTION, DpFunctions_3d9aecd7-8082-4869-a0d1-4a6cdadc4839.xml, DxgkCbSynchronizeExecution, DxgkCbSynchronizeExecution callback function [Display Devices], display.dxgkcbsynchronizeexecution, dispmprt/DxgkCbSynchronizeExecution
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbSynchronizeExecution
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_SYNCHRONIZE_EXECUTION callback


## -description


The <b>DxgkCbSynchronizeExecution</b> function synchronizes a specified function, implemented by the display miniport driver, with the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.


## -prototype


````
DXGKCB_SYNCHRONIZE_EXECUTION DxgkCbSynchronizeExecution;

NTSTATUS DxgkCbSynchronizeExecution(
  _In_  HANDLE                DeviceHandle,
  _In_  PKSYNCHRONIZE_ROUTINE SynchronizeRoutine,
  _In_  PVOID                 Context,
  _In_  ULONG                 MessageNumber,
  _Out_ PBOOLEAN              ReturnValue
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


### -param SynchronizeRoutine [in]

A pointer to a function, implemented by the display miniport driver, that will be synchronized with <i>DxgkDdiInterruptRoutine</i>. The function must conform to the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN SynchronizeRoutine(PVOID Context);</pre>
</td>
</tr>
</table></span></div>

### -param Context [in]

A pointer to a context block, created by the display miniport driver, that will be passed to <i>SynchronizeRoutine</i>.


### -param MessageNumber [in]

The number of the interrupt message with which <i>SynchronizeRoutine</i> will be synchronized. If the interrupt is line-based, this parameter must be zero.


### -param ReturnValue [out]

A pointer to a Boolean variable that receives the return value of <i>SynchronizeRoutine</i>.


## -returns



<b>DxgkCbSynchronizeExecution</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The function was unable to synchronize execution, possibly because the interrupt had not been connected yet.

</td>
</tr>
</table>
 




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>



<a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SYNCHRONIZE_EXECUTION callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

