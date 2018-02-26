---
UID: NC:wdm.KSYNCHRONIZE_ROUTINE
title: KSYNCHRONIZE_ROUTINE
author: windows-driver-content
description: The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine.
old-location: kernel\synchcritsection.htm
old-project: kernel
ms.assetid: 2db9b1b4-0149-4477-9f68-588c55fcbdca
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DrvrRtns_ead80ba6-d012-4140-923c-683d877d5b60.xml, KSYNCHRONIZE_ROUTINE, SynchCritSection, SynchCritSection routine [Kernel-Mode Driver Architecture], kernel.synchcritsection, wdm/SynchCritSection
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


#### Examples

To define a <i>SynchCritSection</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>SynchCritSection</i> callback routine that is named <code>MySynchCritSection</code>, use the KSYNCHRONIZE_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KSYNCHRONIZE_ROUTINE MySynchCritSection;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
  MySynchCritSection(
    PVOID  SynchronizeContext
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The KSYNCHRONIZE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KSYNCHRONIZE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>


