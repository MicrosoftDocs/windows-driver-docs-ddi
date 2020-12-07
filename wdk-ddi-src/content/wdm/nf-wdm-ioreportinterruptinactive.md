---
UID: NF:wdm.IoReportInterruptInactive
title: IoReportInterruptInactive function (wdm.h)
description: The IoReportInterruptInactive routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests.
old-location: kernel\ioreportinterruptinactive.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoReportInterruptInactive function"]
ms.keywords: IoReportInterruptInactive, IoReportInterruptInactive routine [Kernel-Mode Driver Architecture], kernel.ioreportinterruptinactive, wdm/IoReportInterruptInactive
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoReportInterruptInactive
 - wdm/IoReportInterruptInactive
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoReportInterruptInactive
---

# IoReportInterruptInactive function


## -description

The <b>IoReportInterruptInactive</b> routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests.

## -parameters

### -param Parameters 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_report_interrupt_active_state_parameters">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a> structure that contains the connection context associated with the interrupt. The caller received this context from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> call that registered the ISR.

## -remarks

The <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> routine registers an ISR and connects the ISR to an interrupt or interrupts. After the ISR is registered, the driver can make the ISR active or inactive by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptactive">IoReportInterruptActive</a> or <b>IoReportInterruptInactive</b> routine. By default, the ISR is active after the <b>IoConnectInterruptEx</b> call.

An ISR that is in the inactive state can be disconnected or made active. To disconnect the ISR and delete its registration, call the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodisconnectinterruptex">IoDisconnectInterruptEx</a> routine. To make the ISR active without changing its registration, call <b>IoReportInterruptActive</b>.

The <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure must contain a valid connection contect obtained from an <b>IoConnectInterruptEx</b> call. 

For more information about <b>IoReportInterruptInactive</b>, see <a href="/windows-hardware/drivers/kernel/making-an-isr-active-or-inactive">Making an ISR Active or Inactive</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_report_interrupt_active_state_parameters">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodisconnectinterruptex">IoDisconnectInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioreportinterruptactive">IoReportInterruptActive</a>
