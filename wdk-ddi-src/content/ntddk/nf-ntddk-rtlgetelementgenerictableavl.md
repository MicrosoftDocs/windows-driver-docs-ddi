---
UID: NF:ntddk.RtlGetElementGenericTableAvl
title: RtlGetElementGenericTableAvl function (ntddk.h)
description: The RtlGetElementGenericTableAvl routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element.
old-location: ifsk\rtlgetelementgenerictableavl.htm
tech.root: ifsk
ms.assetid: c836dd4b-5c66-4302-9b2a-115cec418533
ms.date: 04/16/2018
keywords: ["RtlGetElementGenericTableAvl function"]
ms.keywords: RtlGetElementGenericTableAvl, RtlGetElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtlgetelementgenerictableavl, ntddk/RtlGetElementGenericTableAvl, rtlref_c94e774b-baba-4be7-be6d-09b01544612b.xml
f1_keywords:
 - "ntddk/RtlGetElementGenericTableAvl"
 - "RtlGetElementGenericTableAvl"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available with Windows XP.
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
- RtlGetElementGenericTableAvl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlGetElementGenericTableAvl function


## -description


The <b>RtlGetElementGenericTableAvl</b> routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element. 


## -parameters




### -param Table [in]

Pointer to the generic AVL table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>) from which the <i>I</i>th element is to be retrieved. The table must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.


### -param I [in]

Index of the element selected. This value is zero-based, so the index of the last-inserted element currently in <i>Table</i> is always one less than the value returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>. 


## -returns



<b>RtlGetElementGenericTableAvl</b> returns a pointer to the caller-supplied data for the <i>I</i>th element in the generic AVL table. It returns <b>NULL</b> if the given <i>I</i> is too large or if the generic AVL table currently has no elements. 




## -remarks



<b>RtlGetElementGenericTableAvl</b> returns the <i>I</i>th element inserted in the generic AVL table. To retrieve the first element, set <i>I</i> to zero. To retrieve the last element, set <i>I</i> to (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>(<i>Table</i>)-1). Note that if an element is deleted from the generic table, the indexes of all elements inserted after the deleted element are decremented. Thus an element's index might change over time. 

<b>RtlGetElementGenericTableAvl</b> is more efficient than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictableavl">RtlLookupElementGenericTableAvl</a> if the caller can supply the index of a particular element for which the caller needs access to the associated data. However, calling <b>RtlGetElementGenericTableAvl</b> repeatedly to test for such an element is less efficient than calling <b>RtlLookupElementGenericTableAvl</b> to locate it. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlGetElementGenericTableAvl</b> routine instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictable">RtlGetElementGenericTable</a>. In the call to <b>RtlGetElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlGetElementGenericTableAvl</b> must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplayingavl">RtlEnumerateGenericTableWithoutSplayingAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictableavl">RtlInsertElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictableavl">RtlLookupElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>
 

 

