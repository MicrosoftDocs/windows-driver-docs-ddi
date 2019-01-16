---
UID: NF:ntddk.RtlLookupElementGenericTable
title: RtlLookupElementGenericTable function
description: The RtlLookupElementGenericTable routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictable.htm
tech.root: ifsk
ms.assetid: 9182084b-ea11-48e4-acb5-06a8375d05bf
ms.date: 04/16/2018
ms.keywords: RtlLookupElementGenericTable, RtlLookupElementGenericTable routine [Installable File System Drivers], ifsk.rtllookupelementgenerictable, ntddk/RtlLookupElementGenericTable, rtlref_609e7ba3-35a1-40e8-9e94-f16605e52155.xml
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlLookupElementGenericTable
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLookupElementGenericTable function


## -description


The <b>RtlLookupElementGenericTable</b> routine searches a generic table for an element that matches the specified data. 


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <b>RtlInitializeGenericTable</b>.


### -param Buffer [in]

A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTable</b>.


## -returns



<b>RtlLookupElementGenericTable</b> returns a pointer to the caller-supplied data for the desired element in the generic table. It returns <b>NULL</b> if the generic table currently has no elements or if no matching element is found. 




## -remarks



If a matching element is found, <b>RtlLookupElementGenericTable</b> rebalances the generic table's splay tree.

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableAvl</b> routine instead of <b>RtlLookupElementGenericTable</b>. In the call to <b>RtlLookupElementGenericTableAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlLookupElementGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553046">RtlIsGenericTableEmpty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553134">RtlNumberGenericTableElements</a>
 

 

