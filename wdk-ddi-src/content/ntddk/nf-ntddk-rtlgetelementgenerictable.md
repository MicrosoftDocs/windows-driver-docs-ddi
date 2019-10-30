---
UID: NF:ntddk.RtlGetElementGenericTable
title: RtlGetElementGenericTable function (ntddk.h)
description: The RtlGetElementGenericTable routine returns a pointer to the caller-supplied data for a particular generic table element.
old-location: ifsk\rtlgetelementgenerictable.htm
tech.root: ifsk
ms.assetid: 85b5fce8-eac4-4cd8-9a24-22564aae915a
ms.date: 04/16/2018
ms.keywords: RtlGetElementGenericTable, RtlGetElementGenericTable routine [Installable File System Drivers], ifsk.rtlgetelementgenerictable, ntddk/RtlGetElementGenericTable, rtlref_5127995d-65ea-4a8b-8b5b-ad64c7cc4c0d.xml
ms.topic: function
f1_keywords:
 - "ntddk/RtlGetElementGenericTable"
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
req.irql: Any level (See Remarks)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlGetElementGenericTable
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGetElementGenericTable function


## -description


The <b>RtlGetElementGenericTable</b> routine returns a pointer to the caller-supplied data for a particular generic table element. 


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>) from which the <i>I</i>th element is to be retrieved. The table must have been initialized by calling <b>RtlInitializeGenericTable</b>.


### -param I [in]

Index of the element selected. This value is zero-based, so the index of the last-inserted element currently in <i>Table</i> is always one less than the value returned by <b>RtlNumberGenericTableElements</b>. 


## -returns



<b>RtlGetElementGenericTable</b> returns a pointer to the caller-supplied data for the <i>I</i>th element in the generic table. It returns <b>NULL</b> if the given <i>I</i> is too large or if the generic table currently has no elements. 




## -remarks



<b>RtlGetElementGenericTable</b> returns the <i>I</i>th element inserted in the generic table. To retrieve the first element, set <i>I</i> to zero. To retrieve the last element, set <i>I</i> to (<b>RtlNumberGenericTableElements</b>(<i>Table</i>)-1). Note that if an element is deleted from the generic table, the indexes of all elements inserted after the deleted element are decremented. Thus an element's index might change over time. 

<b>RtlGetElementGenericTable</b> is more efficient than <b>RtlLookupElementGenericTable</b> if the caller can supply the index of a particular element for which the caller needs access to the associated data. However, calling <b>RtlGetElementGenericTable</b> repeatedly to test for such an element is less efficient than calling <b>RtlLookupElementGenericTable</b> to locate it. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlGetElementGenericTableAvl</b> routine instead of <b>RtlGetElementGenericTable</b>. In the call to <b>RtlGetElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlGetElementGenericTable</b> must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>
 

 

