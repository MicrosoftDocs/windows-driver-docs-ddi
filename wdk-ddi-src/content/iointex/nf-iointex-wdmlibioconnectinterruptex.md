---
UID: NF:iointex.WdmlibIoConnectInterruptEx
title: WdmlibIoConnectInterruptEx function
author: windows-driver-content
description: The WdmlibIoConnectInterruptEx function registers an interrupt-handling routine for a device's interrupts.
old-location: kernel\wdmlibioconnectinterruptex.htm
old-project: kernel
ms.assetid: 172598B1-C486-489F-98F0-382EB8139A08
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoConnectInterruptEx, kernel.wdmlibioconnectinterruptex, iointex/IoConnectInterruptEx, WdmlibIoConnectInterruptEx, WdmlibIoConnectInterruptEx function [Kernel-Mode Driver Architecture], iointex/WdmlibIoConnectInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	WdmlibIoConnectInterruptEx
-	IoConnectInterruptEx
product: Windows
targetos: Windows
req.typenames: LUID
---

# WdmlibIoConnectInterruptEx function


## -description


The <b>WdmlibIoConnectInterruptEx</b> function registers an interrupt-handling routine for a device's interrupts.


## -syntax


````
NTSTATUS WdmlibIoConnectInterruptEx(
  _Inout_ PIO_CONNECT_INTERRUPT_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters [in, out]

Pointer to an <a href="..\wdm\ns-wdm-_io_connect_interrupt_parameters.md">IO_CONNECT_INTERRUPT_PARAMETERS</a> structure that specifies the device and interrupt-handling routine. On return,  <b>WdmlibIoConnectInterruptEx</b> updates this structure to hold information about the device's interrupts.


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
The operation is invalid for the specified device. For example, <i>Parameters</i>-&gt;<b>Version</b> = CONNECT_LINE_BASED, and the system has assigned multiple interrupt messages to the device.

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
The caller specified an invalid value for the <b>Version</b> member of the structure that <i>Parameters</i> points to. <i>Parameters</i>-&gt;<b>Version</b> must be one of CONNECT_LINE_BASED, CONNECT_MESSAGE_BASED, or CONNECT_FULLY_SPECIFIED.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_10</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid value for the tenth member of the structure that <i>Parameters</i> points to. This error occurs, for example, when <i>Parameters</i>-&gt;<b>FullySpecified.ProcessorEnableMask</b> does not have any bits set.

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

Drivers register an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine for line-based interrupts, and an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a> routine for message-signaled interrupts. For more information about how to specify the members of <i>Parameters</i> in each case, see <a href="..\wdm\ns-wdm-_io_connect_interrupt_parameters.md">IO_CONNECT_INTERRUPT_PARAMETERS</a>.

<b>WdmlibIoConnectInterruptEx</b> updates the members of <i>Parameters</i> to provide information about the device's interrupts. For more information about the information provided by <b>WdmlibIoConnectInterruptEx</b>, see <a href="..\wdm\ns-wdm-_io_connect_interrupt_parameters.md">IO_CONNECT_INTERRUPT_PARAMETERS</a>.

Use <a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a> to unregister a routine registered with <b>WdmlibIoConnectInterruptEx</b>.

The driver should not program its device to generate interrupts until it has connected its ISR. Thus, the ISR cannot fire before <b>WdmlibIoConnectInterruptEx</b> returns. However, there are certain devices, such as buttons, that are not programmable. For those devices, the driver should be prepared to handle the ISR as soon as it calls <b>WdmlibIoConnectInterruptEx</b>. The interrupt line may already be asserted when <b>WdmlibIoConnectInterruptEx</b> is called and can fire immediately after the line is enabled at the interrupt controller, before the <b>WdmlibIoConnectInterruptEx</b> call unwinds. 

For more information about registering an interrupt-handling routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560865">Registering an ISR</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547940">InterruptMessageService</a>



<a href="..\wdm\ns-wdm-_io_connect_interrupt_parameters.md">IO_CONNECT_INTERRUPT_PARAMETERS</a>



<a href="..\iointex\nf-iointex-wdmlibiodisconnectinterruptex.md">WdmlibIoDisconnectInterruptEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WdmlibIoConnectInterruptEx function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

