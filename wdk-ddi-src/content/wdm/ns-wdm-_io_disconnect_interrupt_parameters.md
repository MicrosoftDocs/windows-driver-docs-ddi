---
UID: NS:wdm._IO_DISCONNECT_INTERRUPT_PARAMETERS
title: _IO_DISCONNECT_INTERRUPT_PARAMETERS
author: windows-driver-content
description: The IO_DISCONNECT_INTERRUPT_PARAMETERS structure describes the parameters when unregistering an interrupt-handling routine with IoDisconnectInterruptEx.
old-location: kernel\io_disconnect_interrupt_parameters.htm
old-project: kernel
ms.assetid: 646b5442-aff1-4216-bb1b-6988218933be
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _IO_DISCONNECT_INTERRUPT_PARAMETERS, IO_DISCONNECT_INTERRUPT_PARAMETERS, *PIO_DISCONNECT_INTERRUPT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_DISCONNECT_INTERRUPT_PARAMETERS
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: IO_DISCONNECT_INTERRUPT_PARAMETERS, *PIO_DISCONNECT_INTERRUPT_PARAMETERS
req.product: Windows 10 or later.
---

# _IO_DISCONNECT_INTERRUPT_PARAMETERS structure



## -description
The <b>IO_DISCONNECT_INTERRUPT_PARAMETERS</b> structure describes the parameters when unregistering an interrupt-handling routine with <a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>.



## -syntax

````
typedef struct _IO_DISCONNECT_INTERRUPT_PARAMETERS {
  ULONG Version;
  union {
    PVOID                      Generic;
    PKINTERRUPT                InterruptObject;
    PIO_INTERRUPT_MESSAGE_INFO InterruptMessageTable;
  } ConnectionContext;
} IO_DISCONNECT_INTERRUPT_PARAMETERS, *PIO_DISCONNECT_INTERRUPT_PARAMETERS;
````


## -struct-fields

### -field Version

Specifies the particular operation to be performed by <b>IoDisconnectInterruptEx</b>. The value for <b>Version</b> depends on the value specified for <i>Parameters-</i>&gt;<b>Version</b> when <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> registered the interrupt handing routine, as shown in the following table.

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

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> or <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure that was provided by <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> when the interrupt was connected. The value for <b>ConnectionContext</b> depends on the value specified for <i>Parameters</i>-&gt;<b>Version</b> when <b>IoConnectInterruptEx</b> registered the interrupt handling routine, as shown in the following table.

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
 

To minimize casting, <b>ConnectionContext</b> is defined as a union. Use <b>ConnectionContext.Generic</b> to specify the value as a PVOID. Use <b>ConnectionContext.InterruptObject</b> and <b>ConnectionContext.InterruptMessageTable</b> to specify the value as a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> or <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure.


### -field Generic

A pointer to a data structure of unspecified type.


### -field InterruptObject

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure.


### -field InterruptMessageTable

A pointer to an <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure.

</dd>
</dl>

## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_DISCONNECT_INTERRUPT_PARAMETERS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

