---
UID: NF:wdm.IoReportInterruptActive
title: IoReportInterruptActive function
author: windows-driver-content
description: The IoReportInterruptActive routine informs the operating system that a registered interrupt service routine (ISR) is active and ready to handle interrupt requests.
old-location: kernel\ioreportinterruptactive.htm
old-project: kernel
ms.assetid: 41C3AC04-14AF-4C37-9557-F9FF494F234B
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoReportInterruptActive, IoReportInterruptActive routine [Kernel-Mode Driver Architecture], kernel.ioreportinterruptactive, wdm/IoReportInterruptActive
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoReportInterruptActive
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoReportInterruptActive function


## -description


The <b>IoReportInterruptActive</b> routine informs the operating system that a registered interrupt service routine (ISR) is active and ready to handle interrupt requests.


## -syntax


````
VOID IoReportInterruptActive(
  _In_ PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS Parameters
);
````


## -parameters




### -param Parameters [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_report_interrupt_active_state_parameters.md">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a> structure that contains the connection context associated with the interrupt. The caller received this context from the <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> call that registered the ISR.


## -returns



None.




## -remarks



The <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> routine registers an ISR and connects the ISR to an interrupt or interrupts. After the ISR is registered, the driver can make the ISR active or inactive by calling the <b>IoReportInterruptActive</b> or <a href="..\wdm\nf-wdm-ioreportinterruptinactive.md">IoReportInterruptInactive</a> routine. By default, the ISR is active after the <b>IoConnectInterruptEx</b> call.

An ISR that is in the active state can be disconnected or made inactive. To disconnect the ISR and delete its registration, call the <a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a> routine. To make the ISR inactive without changing its registration, call <b>IoReportInterruptInactive</b>.

The <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure must contain a valid connection contect obtained from an <b>IoConnectInterruptEx</b> call. Otherwise, the <b>IoReportInterruptActive</b> routine bug checks in a checked build.

For more information about <b>IoReportInterruptActive</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj158878">Making an ISR Active or Inactive</a>.




## -see-also

<a href="..\wdm\nf-wdm-iodisconnectinterruptex.md">IoDisconnectInterruptEx</a>



<a href="..\wdm\ns-wdm-_io_report_interrupt_active_state_parameters.md">IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</a>



<a href="..\wdm\nf-wdm-ioreportinterruptinactive.md">IoReportInterruptInactive</a>



<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>



 

 


