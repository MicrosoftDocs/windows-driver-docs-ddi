---
UID: NS:wdm._IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
title: _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS (wdm.h)
description: The IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the IoConnectInterruptEx routine.
old-location: kernel\io_report_interrupt_active_state_parameters.htm
tech.root: kernel
ms.assetid: 430B8951-37F0-4173-ACC6-89DB542B4081
ms.date: 04/30/2018
keywords: ["IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure"]
ms.keywords: "*PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure [Kernel-Mode Driver Architecture], PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, kernel.io_report_interrupt_active_state_parameters, wdm/IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, wdm/PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS"
req.header: wdm.h
req.include-header: Wdm.h
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
targetos: Windows
req.typenames: IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, *PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
f1_keywords:
 - _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
 - wdm/_IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
 - PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
 - wdm/PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
 - IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
 - wdm/IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
---

# _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure


## -description

The <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> routine.

## -struct-fields

### -field Version

The interrupt connection type described by this structure. This member must match the connection type the caller obtained from the <b>IoConnectInterruptEx</b> call that connected the interrupt. The following are valid values for this member:

<ul>
<li>CONNECT_FULLY_SPECIFIED</li>
<li>CONNECT_LINE_BASED</li>
<li>CONNECT_MESSAGE_BASED</li>
<li>CONNECT_FULLY_SPECIFIED_GROUP</li>
</ul>
For more information, see Remarks.

### -field ConnectionContext

A union that contains the connection context associated with the interrupt. Each union member is a pointer to a connection context of a particular type. If <b>Version</b> = CONNECT_MESSAGE_BASED, the <b>InterruptMessageTable</b> member of this union contains a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a> structure. For all other <b>Version</b> values, the <b>InterruptObject</b> member of this union contains a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a> structure. Use the <b>Generic</b> member of this union to treat the connection context pointer as a PVOID value (and avoid casting).

For more information, see Remarks.

### -field ConnectionContext.Generic

A PVOID pointer to a connection context.

### -field ConnectionContext.InterruptObject

A pointer to a connection context of type <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KINTERRUPT</a>.

### -field ConnectionContext.InterruptMessageTable

A pointer to a connection context of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>.

## -remarks

This structure is supplied as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptactive">IoReportInterruptActive</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptinactive">IoReportInterruptInactive</a> routines.

The <b>Version</b> member indicates the type of the connection context specified in the <b>ConnectionContext</b> member. Set this member to the <i>Parameters-</i>><b>Version</b> value obtained from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> call that connected the interrupt.

If the <i>Parameters-</i>><b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_FULLY_SPECIFIED or CONNECT_FULLY_SPECIFIED_GROUP, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>><b>FullySpecified.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>><b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_MESSAGE_BASED, set the <b>ConnectionContext.InterruptMessageTable</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>><b>MessageBased.ConnectionContext.InterruptMessageTable</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>><b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_LINE_BASED, but the caller initially set <i>Parameters-</i>><b>Version</b> to CONNECT_MESSAGE_BASED, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>><b>MessageBased.ConnectionContext.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>><b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_LINE_BASED, and the caller initially set <i>Parameters-</i>><b>Version</b> to CONNECT_LINE_BASED, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>><b>LineBased.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptactive">IoReportInterruptActive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptinactive">IoReportInterruptInactive</a>

