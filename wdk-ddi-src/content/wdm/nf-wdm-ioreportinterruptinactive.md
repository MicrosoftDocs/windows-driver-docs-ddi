---
UID: NF:wdm.IoReportInterruptInactive
title: IoReportInterruptInactive function
author: windows-driver-content
description: The IoReportInterruptInactive routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests.
old-location: kernel\ioreportinterruptinactive.htm
old-project: kernel
ms.assetid: 614ECB39-E1D0-4BF0-B3C8-635BADD05508
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoReportInterruptInactive, IoReportInterruptInactive routine [Kernel-Mode Driver Architecture], wdm/IoReportInterruptInactive, kernel.ioreportinterruptinactive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoReportInterruptInactive
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReportInterruptInactive function


## -description


The <b>IoReportInterruptInactive</b> routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests.


## -syntax


````
VOID IoReportInterruptInactive(
  _In_ PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_report_interrupt_active_state_parameters.md">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a> structure that contains the connection context associated with the interrupt. The caller received this context from the <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> call that registered the ISR.


## -returns



None.




## -remarks



The <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine registers an ISR and connects the ISR to an interrupt or interrupts. After the ISR is registered, the driver can make the ISR active or inactive by calling the <a href="..\wdm\nf-wdm-ioreportinterruptactive.md">IoReportInterruptActive</a> or <b>IoReportInterruptInactive</b> routine. By default, the ISR is active after the <b>IoConnectInterruptEx</b> call.

An ISR that is in the inactive state can be disconnected or made active. To disconnect the ISR and delete its registration, call the <a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a> routine. To make the ISR active without changing its registration, call <b>IoReportInterruptActive</b>.

The <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure must contain a valid connection contect obtained from an <b>IoConnectInterruptEx</b> call. Otherwise, the <b>IoReportInterruptInactive</b> routine bug checks in a checked build.

For more information about <b>IoReportInterruptInactive</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj158878">Making an ISR Active or Inactive</a>.




## -see-also

<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>



<a href="..\wdm\nf-wdm-ioreportinterruptactive.md">IoReportInterruptActive</a>



<a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>



<a href="..\wdm\ns-wdm-_io_report_interrupt_active_state_parameters.md">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReportInterruptInactive routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

