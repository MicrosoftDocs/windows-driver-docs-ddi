---
UID: NC:ntddk.RTL_RUN_ONCE_INIT_FN
title: RTL_RUN_ONCE_INIT_FN
author: windows-driver-content
description: The RunOnceInitialization routine performs a one-time initialization operation.
old-location: kernel\runonceinitialization.htm
tech.root: kernel
ms.assetid: 7411c10f-76ab-44df-8cab-2266443417aa
ms.date: 04/30/2018
ms.keywords: DrvrRtns_2bf4e129-77ac-4525-9504-4f039a503943.xml, RTL_RUN_ONCE_INIT_FN, RunOnceInitialization, RunOnceInitialization routine [Kernel-Mode Driver Architecture], kernel.runonceinitialization, ntddk/RunOnceInitialization
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Drivers can implement the RunOnceInitialization routine only on Windows Vista and later versions of Windows.
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
req.irql: Called at IRQL <= APC_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	RunOnceInitialization
product:
- Windows
targetos: Windows
req.typenames: 
---

# RTL_RUN_ONCE_INIT_FN callback function


## -description


The <i>RunOnceInitialization</i> routine performs a one-time initialization operation.


## -parameters




### -param RunOnce [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a> one-time initialization structure that the driver previously passed as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562765">RtlRunOnceExecuteOnce</a> routine that called this <i>RunOnceInitialization</i> routine.


### -param Context [out]

A pointer to a PVOID variable to which the routine writes the initialization data.


### -param Parameter [in, out]

The <i>Parameter</i> value that the driver passed to the <b>RtlRunOnceExecuteOnce</b> routine that called this <i>RunOnceInitialization</i> routine.


## -returns




      The <i>RunOnceInitialization</i> routine returns a nonzero value to indicate success, and returns zero to indicate failure.




## -remarks



A driver-implemented <i>RunOnceInitialization</i> routine performs driver-specific initialization and then writes the initialization data to the memory location that the <i>Context</i> parameter points to. Drivers use the <b>RtlRunOnceExecuteOnce</b> routine to make a one-time call to a <i>RunOnceInitialization</i> routine. The operating system guarantees that the <i>RunOnceInitialization</i> routine is not called twice for the same value of the <i>RunOnce</i> parameter.

A small number of low-order bits in the location pointed to by the <i>Context</i> parameter are reserved for use by the operating system. Your driver's <i>RunOnceInitialization</i> routine should set these reserved bits to zero in the output value that it writes to *<i>Context</i>. The RTL_RUN_ONCE_CTX_RESERVED_BITS constant defined in Ntddk.h specifies the number of low-order bits that are reserved. Currently, RTL_RUN_ONCE_CTX_RESERVED_BITS is defined to be two, which means that the driver must set the two least significant bits of the PVOID value pointed to by <i>Context</i> to zero.


#### Examples

To define a <i>RunOnceInitialization</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>RunOnceInitialization</i> callback routine that is named <code>MyRunOnceInitialization</code>, use the RTL_RUN_ONCE_INIT_FN type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RTL_RUN_ONCE_INIT_FN MyRunOnceInitialization;</pre>
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
ULONG 
  MyRunOnceInitialization(
    PRTL_RUN_ONCE  RunOnce,
    PVOID  Parameter,
    PVOID  *Context
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The RTL_RUN_ONCE_INIT_FN function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the RTL_RUN_ONCE_INIT_FN function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563626">RTL_RUN_ONCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562759">RtlRunOnceBeginInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562763">RtlRunOnceComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562765">RtlRunOnceExecuteOnce</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562767">RtlRunOnceInitialize</a>
 

 

