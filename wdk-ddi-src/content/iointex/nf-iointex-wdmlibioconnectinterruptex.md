---
UID: NF:iointex.WdmlibIoConnectInterruptEx
title: WdmlibIoConnectInterruptEx function (iointex.h)
description: The WdmlibIoConnectInterruptEx function registers an interrupt-handling routine for a device's interrupts.
old-location: kernel\wdmlibioconnectinterruptex.htm
tech.root: kernel
ms.assetid: 172598B1-C486-489F-98F0-382EB8139A08
ms.date: 04/30/2018
ms.keywords: IoConnectInterruptEx, WdmlibIoConnectInterruptEx, WdmlibIoConnectInterruptEx function [Kernel-Mode Driver Architecture], iointex/IoConnectInterruptEx, iointex/WdmlibIoConnectInterruptEx, kernel.wdmlibioconnectinterruptex
ms.topic: function
req.header: iointex.h
req.include-header: Iointex.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system. Drivers that must also work on Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- WdmlibIoConnectInterruptEx
- IoConnectInterruptEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdmlibIoConnectInterruptEx function


## -description


The <b>WdmlibIoConnectInterruptEx</b> function registers an interrupt-handling routine for a device's interrupts.


## -parameters




### -param Parameters [in, out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550541">IO_CONNECT_INTERRUPT_PARAMETERS</a> structure that specifies the device and interrupt-handling routine. On return,  <b>WdmlibIoConnectInterruptEx</b> updates this structure to hold information about the device's interrupts.


## -returns



The function returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error value on failure. Possible error values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The operation is invalid for the specified device. For example, <i>Parameters</i>-><b>Version</b> = CONNECT_LINE_BASED, and the system has assigned multiple interrupt messages to the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid parameter. This error occurs, for example, when the caller specified <b>NULL</b> for the device's device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for the <b>Version</b> member of the structure that <i>Parameters</i> points to. <i>Parameters</i>-><b>Version</b> must be one of CONNECT_LINE_BASED, CONNECT_MESSAGE_BASED, or CONNECT_FULLY_SPECIFIED.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_10</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for the tenth member of the structure that <i>Parameters</i> points to. This error occurs, for example, when <i>Parameters</i>-><b>FullySpecified.ProcessorEnableMask</b> does not have any bits set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
One of the arguments was not found. For example, the specified device has no interrupts, or the specified interrupt vector is not assigned to any device.

</td>
</tr>
</table>
 




## -remarks



<b>WdmlibIoConnectInterruptEx</b>
           can be used to register an interrupt-handling routine for both traditional line-based interrupts (such as that supported by the PCI bus), and the newer message-signaled interrupts (such as that supported by PCI versions 2.2 and 3.0). 

Drivers register an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine for line-based interrupts, and an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a> routine for message-signaled interrupts. For more information about how to specify the members of <i>Parameters</i> in each case, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550541">IO_CONNECT_INTERRUPT_PARAMETERS</a>.

<b>WdmlibIoConnectInterruptEx</b> updates the members of <i>Parameters</i> to provide information about the device's interrupts. For more information about the information provided by <b>WdmlibIoConnectInterruptEx</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550541">IO_CONNECT_INTERRUPT_PARAMETERS</a>.

Use <a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a> to unregister a routine registered with <b>WdmlibIoConnectInterruptEx</b>.

The driver should not program its device to generate interrupts until it has connected its ISR. Thus, the ISR cannot fire before <b>WdmlibIoConnectInterruptEx</b> returns. However, there are certain devices, such as buttons, that are not programmable. For those devices, the driver should be prepared to handle the ISR as soon as it calls <b>WdmlibIoConnectInterruptEx</b>. The interrupt line may already be asserted when <b>WdmlibIoConnectInterruptEx</b> is called and can fire immediately after the line is enabled at the interrupt controller, before the <b>WdmlibIoConnectInterruptEx</b> call unwinds. 

For more information about registering an interrupt-handling routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560865">Registering an ISR</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550541">IO_CONNECT_INTERRUPT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a>



<a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a>
 

 

