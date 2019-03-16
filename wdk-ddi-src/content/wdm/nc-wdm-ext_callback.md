---
UID: NC:wdm.EXT_CALLBACK
title: EXT_CALLBACK (wdm.h)
description: An ExTimerCallback callback routine runs after an EX_TIMER timer object's time interval expires.
old-location: kernel\extimercallback.htm
tech.root: kernel
ms.assetid: 4BE0A753-58A6-4868-9A04-B9A0710A02A5
ms.date: 04/30/2018
ms.keywords: EXT_CALLBACK, ExTimerCallback, ExTimerCallback routine [Kernel-Mode Driver Architecture], kernel.extimercallback, wdm/ExTimerCallback
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- ExTimerCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# EXT_CALLBACK callback function


## -description


An <i>ExTimerCallback</i> callback routine runs after an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> timer object's time interval expires.


## -parameters




### -param Timer [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure. This structure is a timer object that was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.


### -param Context [in]

The context value that your driver previously supplied as the <i>CallbackContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.


## -returns



None.




## -remarks



As an option, your driver can supply a pointer to an <i>ExTimerCallback</i> routine in the <i>Callback</i> parameter that your driver passes to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine. After the timer expires, the operating system calls the <i>ExTimerCallback</i> routine.

To start a timer operation, the driver passes the timer object as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a> routine. After the timer expires, the operating system schedules the <i>ExTimerCallback</i> routine to run.

A timer object is a waitable object. A driver thread can call a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a> to wait for the timer to expire. When the timer expires, the operating system signals the timer object.

A timer might be canceled before it expires. The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265180">ExCancelTimer</a> routine to explicitly cancel a timer. If the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a> routine to start a new timer on a timer object before a previously set timer on this object expires, this call implicitly cancels the previous timer and then starts the new timer.

An <i>ExTimerCallback</i> routine can call a routine such as <b>ExSetTimer</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn265181">ExDeleteTimer</a>. If an <i>ExTimerCallback</i> routine calls <b>ExDeleteTimer</b>, the <i>Wait</i> parameter supplied in this call must be <b>FALSE</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265175">Deleting a System-Allocated Timer Object</a>.

In a multiprocessor system, <i>ExTimerCallback</i> callbacks for two successive expirations of a periodic timer might simultaneously run on two different processors.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.


#### Examples

To define an <i>ExTimerCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function type helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>ExTimerCallback</i> callback routine that is named <code>MyExTimerCallback</code>, use the EXT_CALLBACK function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EXT_CALLBACK  MyExTimerCallback;</pre>
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
VOID
  MyExTimerCallback(
    PEX_TIMER  Timer,
    PVOID  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The EXT_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the <b>_Use_decl_annotations_</b> annotation to your function definition. The <b>_Use_decl_annotations_</b> annotation ensures that the annotations that are applied to the EXT_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions Using Function Role Types for WDM Drivers</a>. For more information about <b>_Use_decl_annotations_</b>, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265180">ExCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

