---
UID: NC:wdm.EXT_DELETE_CALLBACK
title: EXT_DELETE_CALLBACK
author: windows-driver-content
description: An ExTimerDeleteCallback callback routine runs when the operating system deletes an EX_TIMER timer object.
old-location: kernel\extimerdeletecallback.htm
tech.root: kernel
ms.assetid: 6066CDD4-D2BA-4CF8-AF1C-189812B150D5
ms.date: 04/30/2018
ms.keywords: EXT_DELETE_CALLBACK, ExTimerDeleteCallback, ExTimerDeleteCallback routine [Kernel-Mode Driver Architecture], kernel.extimerdeletecallback, wdm/ExTimerDeleteCallback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	ExTimerDeleteCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# EXT_DELETE_CALLBACK callback function


## -description


An <i>ExTimerDeleteCallback</i> callback routine runs when the operating system deletes an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> timer object.


## -parameters




### -param Context [in, optional]

The context value from the <i>DeleteContext</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265194">EXT_DELETE_PARAMETERS</a> structure that your driver previously passed as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265181">ExDeleteTimer</a> routine.


## -returns



None.




## -remarks



As an option, your driver can supply a pointer to an <i>ExTimerDeleteCallback</i> routine in the <i>DeleteCallback</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265194">EXT_DELETE_PARAMETERS</a> structure that your driver passes as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265181">ExDeleteTimer</a> routine. The <i>ExTimerDeleteCallback</i> routine can free any storage or other system resources that the driver might have previously allocated to use with the timer object that is being deleted.

If the driver supplies an <i>ExTimerDeleteCallback</i> routine, and the <i>Wait</i> parameter in the <b>ExDeleteRoutine</b> call is <b>TRUE</b>, the <i>ExTimerDeleteCallback</i> routine runs before <b>ExDeleteTimer</b> returns. Otherwise, the  <i>ExTimerDeleteCallback</i> routine might run before or after the <b>ExDeleteTimer</b> call returns. The  <i>ExTimerDeleteCallback</i> routine is called only after the timer object has been disabled to prevent further timer operations and any pending timer operation on the timer object is canceled or completed. The timer object (an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a> structure) that the driver passes as an input parameter to the <b>ExDeleteTimer</b> routine might no longer be valid by the time the <i>ExTimerDeleteCallback</i> routine runs.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.


#### Examples

To define an <i>ExTimerDeleteCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function type helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>ExTimerDeleteCallback</i> callback routine that is named <code>MyExTimerDeleteCallback</code>, use the EXT_DELETE_CALLBACK function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EXT_DELETE_CALLBACK  MyExTimerDeleteCallback;</pre>
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
  MyExTimerDeleteCallback(
    PVOID  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The EXT_DELETE_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the <b>_Use_decl_annotations_</b> annotation to your function definition. The <b>_Use_decl_annotations_</b> annotation ensures that the annotations that are applied to the EXT_DELETE_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions Using Function Role Types for WDM Drivers</a>. For more information about <b>_Use_decl_annotations_</b>, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265194">EXT_DELETE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/exxxxtimer-routines-and-ex-timer-objects">EX_TIMER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265181">ExDeleteTimer</a>
 

 

