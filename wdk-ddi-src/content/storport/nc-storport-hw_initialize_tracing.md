---
UID: NC:storport.HW_INITIALIZE_TRACING
title: HW_INITIALIZE_TRACING
author: windows-driver-content
description: The HwStorInitializeTracing callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.
old-location: storage\hwstorinitializetracing.htm
old-project: storage
ms.assetid: e0d4ea58-415b-4ea4-9001-8a23ab44a1bf
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_INITIALIZE_TRACING, HwStorInitializeTracing, HwStorInitializeTracing routine [Storage Devices], storage.hwstorinitializetracing, storport/HwStorInitializeTracing, storvmini_0c53c6e6-7c5c-4400-b923-c03a7756614f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorInitializeTracing
product: Windows
targetos: Windows
req.typenames: 
---

# HW_INITIALIZE_TRACING callback function


## -description


The <b>HwStorInitializeTracing</b> callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.


## -parameters




### -param Arg1

The first parameter that is passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>.


### -param Arg2

The second parameter that is passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>.


## -returns



None




## -remarks



The name <b>HwStorInitializeTracing</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_INITIALIZE_TRACING (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport's <b>HwStorInitializeTracing</b> at PASSIVE_LEVEL.


#### Examples

To define an <b>HwStorInitializeTracing</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorInitializeTracing</b> callback routine that is named <i>MyHwInitializeTracing</i>, use the <b>HW_INITIALIZE_TRACING</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_INITIALIZE_TRACING MyHwInitializeTracing;</pre>
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
MyHwInitializeTracing (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_INITIALIZE_TRACING</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_INITIALIZE_TRACING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.

<div class="code"></div>


