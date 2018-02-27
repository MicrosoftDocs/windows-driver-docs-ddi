---
UID: NC:ntddk.EXPAND_STACK_CALLOUT
title: EXPAND_STACK_CALLOUT
author: windows-driver-content
description: The ExpandedStackCall routine executes with a guaranteed stack size.
old-location: kernel\expandedstackcall.htm
old-project: kernel
ms.assetid: ca9af049-f183-458c-b43f-891678a7be5e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DrvrRtns_2b43fd11-2258-4b8d-adb7-58dcc5d37897.xml, EXPAND_STACK_CALLOUT, ExpandedStackCall, ExpandedStackCall routine [Kernel-Mode Driver Architecture], kernel.expandedstackcall, ntddk/ExpandedStackCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ntddk.h
apiname:
-	ExpandedStackCall
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# EXPAND_STACK_CALLOUT callback


## -description


The <i>ExpandedStackCall</i> routine executes with a guaranteed stack size.


## -prototype


````
EXPAND_STACK_CALLOUT ExpandedStackCall;

VOID ExpandedStackCall(
  _In_opt_ PVOID Parameter
)
{ ... }
````


## -parameters




### -param Parameter [in, optional]

The value passed to the <a href="..\ntddk\nf-ntddk-keexpandkernelstackandcallout.md">KeExpandKernelStackAndCallout</a> routine that executed <i>ExpandedStackCall</i>.


## -returns



None




## -remarks



The <i>ExpandedStackCall</i> routine must handle all exceptions. Any unhandled exception causes the system to bug check with <a href="https://msdn.microsoft.com/library/windows/hardware/ff557408">Bug Check 0x1E: KMODE_EXCEPTION_NOT_HANDLED</a>.

If the <i>ExpandedStackCall</i> changes the current IRQL, it must restore the original value before returning. 


#### Examples

To define an <i>ExpandedStackCall</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
The EXPAND_STACK_CALLOUT function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EXPAND_STACK_CALLOUT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\ntddk\nf-ntddk-keexpandkernelstackandcallout.md">KeExpandKernelStackAndCallout</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExpandedStackCall routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

