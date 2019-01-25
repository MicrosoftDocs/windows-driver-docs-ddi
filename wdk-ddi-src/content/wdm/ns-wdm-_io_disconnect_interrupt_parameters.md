---
UID: NS:wdm._IO_DISCONNECT_INTERRUPT_PARAMETERS
title: "_IO_DISCONNECT_INTERRUPT_PARAMETERS" (wdm.h)
description: The IO_DISCONNECT_INTERRUPT_PARAMETERS structure describes the parameters when unregistering an interrupt-handling routine with IoDisconnectInterruptEx.
old-location: kernel\io_disconnect_interrupt_parameters.htm
tech.root: kernel
ms.assetid: 646b5442-aff1-4216-bb1b-6988218933be
ms.date: 04/30/2018
ms.keywords: "*PIO_DISCONNECT_INTERRUPT_PARAMETERS, IO_DISCONNECT_INTERRUPT_PARAMETERS, IO_DISCONNECT_INTERRUPT_PARAMETERS structure [Kernel-Mode Driver Architecture], PIO_DISCONNECT_INTERRUPT_PARAMETERS, PIO_DISCONNECT_INTERRUPT_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], _IO_DISCONNECT_INTERRUPT_PARAMETERS, kernel.io_disconnect_interrupt_parameters, kstruct_b_f8b627a3-a9ce-4a6c-8e3a-c0354ecdff7f.xml, wdm/IO_DISCONNECT_INTERRUPT_PARAMETERS, wdm/PIO_DISCONNECT_INTERRUPT_PARAMETERS"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IO_DISCONNECT_INTERRUPT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: IO_DISCONNECT_INTERRUPT_PARAMETERS, *PIO_DISCONNECT_INTERRUPT_PARAMETERS
---

# _IO_DISCONNECT_INTERRUPT_PARAMETERS structure


## -description


The <b>IO_DISCONNECT_INTERRUPT_PARAMETERS</b> structure describes the parameters when unregistering an interrupt-handling routine with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549093">IoDisconnectInterruptEx</a>.


## -struct-fields




### -field Version

Specifies the particular operation to be performed by <b>IoDisconnectInterruptEx</b>. The value for <b>Version</b> depends on the value specified for <i>Parameters-</i>&gt;<b>Version</b> when <a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a> registered the interrupt handing routine, as shown in the following table.

<table>
<tr>
<th>IO_CONNECT_INTERRUPT_PARAMETERS Version value</th>
<th>IO_DISCONNECT_INTERRUPT_PARAMETERS Version value</th>
</tr>
<tr>
<td>
CONNECT_LINE_BASED

</td>
<td>
CONNECT_LINE_BASED

</td>
</tr>
<tr>
<td>
CONNECT_MESSAGE_BASED

</td>
<td>
The value of <b>Version</b> output by <b>IoConnectInterruptEx</b>.

</td>
</tr>
<tr>
<td>
CONNECT_FULLY_SPECIFIED

</td>
<td>
CONNECT_FULLY_SPECIFIED

</td>
</tr>
</table>
 


### -field ConnectionContext

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550576">IO_INTERRUPT_MESSAGE_INFO</a> structure that was provided by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548378">IoConnectInterruptEx</a> when the interrupt was connected. The value for <b>ConnectionContext</b> depends on the value specified for <i>Parameters</i>-&gt;<b>Version</b> when <b>IoConnectInterruptEx</b> registered the interrupt handling routine, as shown in the following table.

<table>
<tr>
<th>IoConnectInterruptEx Version value</th>
<th>IoDisconnectInterruptEx ConnectionContext value</th>
</tr>
<tr>
<td>
CONNECT_LINE_BASED

</td>
<td>
The value stored in <b>LineBased.InterruptObject</b>.

</td>
</tr>
<tr>
<td>
CONNECT_MESSAGE_BASED

</td>
<td>
The value stored in <b>MessageBased.ConnectionContext</b>.

</td>
</tr>
<tr>
<td>
CONNECT_FULLY_SPECIFIED

</td>
<td>
The value stored in <b>FullySpecified.InterruptObject</b>.

</td>
</tr>
</table>
 

To minimize casting, <b>ConnectionContext</b> is defined as a union. Use <b>ConnectionContext.Generic</b> to specify the value as a PVOID. Use <b>ConnectionContext.InterruptObject</b> and <b>ConnectionContext.InterruptMessageTable</b> to specify the value as a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550576">IO_INTERRUPT_MESSAGE_INFO</a> structure.


### -field ConnectionContext.Generic

A pointer to a data structure of unspecified type.


### -field ConnectionContext.InterruptObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure.


### -field ConnectionContext.InterruptMessageTable

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550576">IO_INTERRUPT_MESSAGE_INFO</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550576">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549093">IoDisconnectInterruptEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>
 

 

