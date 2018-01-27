---
UID: NC:wdm.KSYNCHRONIZE_ROUTINE
title: KSYNCHRONIZE_ROUTINE
author: windows-driver-content
description: The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine.
old-location: kernel\synchcritsection.htm
old-project: kernel
ms.assetid: 2db9b1b4-0149-4477-9f68-588c55fcbdca
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.synchcritsection, SynchCritSection routine [Kernel-Mode Driver Architecture], SynchCritSection, KSYNCHRONIZE_ROUTINE, KSYNCHRONIZE_ROUTINE, wdm/SynchCritSection, DrvrRtns_ead80ba6-d012-4140-923c-683d877d5b60.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: Called at DIRQL (see Remarks section).
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdm.h
apiname: 
-	SynchCritSection
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# KSYNCHRONIZE_ROUTINE callback


## -description


The <i>SynchCritSection</i> routine is used to access hardware resources or driver data that are shared with a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine.


## -prototype


````
KSYNCHRONIZE_ROUTINE SynchCritSection;

BOOLEAN SynchCritSection(
  _In_ PVOID SynchronizeContext
)
{ ... }
````


## -parameters




### -param SynchronizeContext [in]

Caller-supplied context information, specified by the driver's call to <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>.


## -returns


If the routine's operation succeeds, the routine should return <b>TRUE</b>; otherwise, it should return <b>FALSE</b>. (Success and failure of this routine are driver-defined.) The specified return value becomes the return value for <b>KeSynchronizeExecution</b>.



## -remarks


Drivers must use <i>SynchCritSection</i> routines to access hardware resources or driver data that can also be accessed by an <i>InterruptService</i> routine (ISR).

The system calls a driver's <i>SynchCritSection</i> routine when the driver calls <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>. When a driver calls <b>KeSynchronizeExecution</b>, it specifies the address of a <i>SynchCritSection</i> routine, context information for the routine, and an interrupt object pointer. The <b>KeSynchronizeExecution</b> routine acquires the interrupt object's spin lock, then calls the <i>SynchCritSection</i> routine.

A driver's <i>SynchCritSection</i> routine executes at the same IRQL as the ISR with which it is associated. Specifically, it executes at some system-assigned <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">DIRQL</a>, as specified by the <i>SynchronizeIrql</i> parameter to <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>. (Other devices, with higher DIRQL values, can interrupt a <i>SynchCritSection</i> routine.)


