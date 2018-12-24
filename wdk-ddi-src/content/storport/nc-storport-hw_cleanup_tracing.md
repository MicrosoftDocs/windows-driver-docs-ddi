---
UID: NC:storport.HW_CLEANUP_TRACING
title: HW_CLEANUP_TRACING
description: The HwStorCleanupTracing callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.
old-location: storage\hwstorcleanuptracing.htm
tech.root: storage
ms.assetid: 878a7c4f-8584-4de2-9a32-f1c358d9b27f
ms.date: 03/29/2018
ms.keywords: HW_CLEANUP_TRACING, HwStorCleanupTracing, HwStorCleanupTracing routine [Storage Devices], storage.hwstorcleanuptracing, storport/HwStorCleanupTracing, storvmini_7a5c9359-04e5-4ad4-b638-14cce4087df2.xml
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
-	HwStorCleanupTracing
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_CLEANUP_TRACING callback function


## -description


The <b>HwStorCleanupTracing</b> callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.


## -parameters




### -param Arg1

A pointer to the driver object.


## -returns



None




## -remarks



The name <b>HwStorCleanupTracing</b> is  placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_CLEANUP_TRACING (
  IN PVOID  Arg1
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport's <b>HwStorCleanupTracing</b> at PASSIVE_LEVEL.


#### Examples

To define an <b>HwStorCleanupTracing</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorCleanupTracing</b> callback routine that is named <i>MyHwCleanupTracing</i>, use the <b>HW_CLEANUP_TRACING</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_CLEANUP_TRACING MyHwCleanupTracing;</pre>
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
MyHwCleanupTracing (
  _In_ PVOID  Arg1
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_CLEANUP_TRACING</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_CLEANUP_TRACING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/jj159529.aspx">Annotating Function Behavior</a>.



