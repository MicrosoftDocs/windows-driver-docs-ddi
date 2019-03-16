---
UID: NF:ntddk.RtlEnumerateGenericTableWithoutSplaying
title: RtlEnumerateGenericTableWithoutSplaying function (ntddk.h)
description: The RtlEnumerateGenericTableWithoutSplaying routine is used to enumerate the elements in a generic table.
old-location: ifsk\rtlenumerategenerictablewithoutsplaying.htm
tech.root: ifsk
ms.assetid: 28dacbac-99f0-415d-8d4f-954220839078
ms.date: 04/16/2018
ms.keywords: RtlEnumerateGenericTableWithoutSplaying, RtlEnumerateGenericTableWithoutSplaying routine [Installable File System Drivers], ifsk.rtlenumerategenerictablewithoutsplaying, ntddk/RtlEnumerateGenericTableWithoutSplaying, rtlref_83b2461b-003b-4aee-be45-afb325b15219.xml
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XPand later versions of the Windows operating systems.
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlEnumerateGenericTableWithoutSplaying
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlEnumerateGenericTableWithoutSplaying function


## -description


The <b>RtlEnumerateGenericTableWithoutSplaying</b> routine is used to enumerate the elements in a generic table. 


## -parameters




### -param Table [in]

A pointer to the generic table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>.


### -param RestartKey [in, out]

An address of the element returned by the previous call to <b>RtlEnumerateGenericTableWithoutSplaying</b>. Should be set to <b>NULL</b> if the enumeration is to start at the first element in the table. 

To enumerate all elements in the table, use <b>RtlEnumerateGenericTableWithoutSplaying</b> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RestartKey = NULL;
for (ptr = RtlEnumerateGenericTableWithoutSplaying(Table, &amp;RestartKey);
     ptr != NULL;
     ptr = RtlEnumerateGenericTableWithoutSplaying(Table, &amp;RestartKey)) {
        // Process the element pointed to by ptr
}</pre>
</td>
</tr>
</table></span></div>

## -returns



<b>RtlEnumerateGenericTableWithoutSplaying</b> returns a pointer to the caller-defined structure associated with the element. It returns <b>NULL</b> if <i>RestartKey</i> is <b>NULL</b> and the table has no elements or if <i>RestartKey</i> is a returned pointer and there is no next element. 




## -remarks



Unlike <a href="https://msdn.microsoft.com/library/windows/hardware/ff552243">RtlEnumerateGenericTable</a>, <b>RtlEnumerateGenericTableWithoutSplaying</b> does not flatten the generic table by converting it from a splay tree into a sorted linked list. <b>RtlEnumerateGenericTableWithoutSplaying</b> is more efficient and multiprocessor-safe than <b>RtlEnumerateGenericTable</b>. 

<b>RtlEnumerateGenericTableWithoutSplaying</b> can be called repeatedly to process the caller's data in each element of a generic table. 

Callers of the <i>Rtl..GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlEnumerateGenericTableWithoutSplaying</b> routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406462">RtlEnumerateGenericTableWithoutSplayingAvl</a>. In the call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlEnumerateGenericTableWithoutSplaying</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552243">RtlEnumerateGenericTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553046">RtlIsGenericTableEmpty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553134">RtlNumberGenericTableElements</a>
 

 

