---
UID: NC:ntddk.EXPAND_STACK_CALLOUT
title: EXPAND_STACK_CALLOUT (ntddk.h)
description: The ExpandedStackCall routine executes with a guaranteed stack size.
old-location: kernel\expandedstackcall.htm
tech.root: kernel
ms.assetid: ca9af049-f183-458c-b43f-891678a7be5e
ms.date: 04/30/2018
keywords: ["EXPAND_STACK_CALLOUT callback function"]
ms.keywords: DrvrRtns_2b43fd11-2258-4b8d-adb7-58dcc5d37897.xml, EXPAND_STACK_CALLOUT, ExpandedStackCall, ExpandedStackCall routine [Kernel-Mode Driver Architecture], kernel.expandedstackcall, ntddk/ExpandedStackCall
f1_keywords:
 - "ntddk/ExpandedStackCall"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Drivers can implement ExpandedStackCall routines on Windows Server 2003 for an x64-based processor, and on Windows Vista and later versions of Windows for all processors.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- ExpandedStackCall
product:
- Windows
targetos: Windows
req.typenames: 
---

# EXPAND_STACK_CALLOUT callback function


## -description


The <i>ExpandedStackCall</i> routine executes with a guaranteed stack size.


## -parameters




### -param Parameter [in, optional]

The value passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout">KeExpandKernelStackAndCallout</a> routine that executed <i>ExpandedStackCall</i>.


## -returns



None




## -remarks



The <i>ExpandedStackCall</i> routine must handle all exceptions. Any unhandled exception causes the system to bug check with <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0x1e--kmode-exception-not-handled">Bug Check 0x1E: KMODE_EXCEPTION_NOT_HANDLED</a>.

If the <i>ExpandedStackCall</i> changes the current IRQL, it must restore the original value before returning. 


#### Examples

To define an <i>ExpandedStackCall</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>ExpandedStackCall</i> callback routine that is named <code>MyExpandedStackCall</code>, use the EXPAND_STACK_CALLOUT type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EXPAND_STACK_CALLOUT MyExpandedStackCall;</pre>
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
  MyExpandedStackCall(
    PVOID  Parameter
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The EXPAND_STACK_CALLOUT function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EXPAND_STACK_CALLOUT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout">KeExpandKernelStackAndCallout</a>
 

 

