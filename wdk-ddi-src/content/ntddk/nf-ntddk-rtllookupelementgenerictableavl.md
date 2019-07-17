---
UID: NF:ntddk.RtlLookupElementGenericTableAvl
title: RtlLookupElementGenericTableAvl function (ntddk.h)
description: The RtlLookupElementGenericTableAvl routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictableavl.htm
tech.root: ifsk
ms.assetid: 7A10B5E7-293E-4E28-BAB8-E189891A851A
ms.date: 04/16/2018
ms.keywords: RtlLookupElementGenericTableAvl, RtlLookupElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtllookupelementgenerictableavl, ntddk/RtlLookupElementGenericTableAvl
ms.topic: function
f1_keywords:
 - "ntddk/RtlLookupElementGenericTableAvl"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlLookupElementGenericTableAvl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLookupElementGenericTableAvl function


## -description


The <b>RtlLookupElementGenericTableAvl</b> routine searches a generic table for an element that matches the specified data.


## -parameters




### -param Table [in]

Pointer to the generic Adelson-Velsky/Landis (AVL) table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.


### -param Buffer [in]

A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTableAvl</b>.


## -returns



<b>RtlLookupElementGenericTableAvl</b> returns a pointer to the user data that is associated with the matching element in the generic table, or <b>NULL</b> if the generic table currently has no elements or if no matching element is found.




## -remarks



By default, the operating system uses splay trees to implement generic tables, but the <b>RtlLookupElementGenericTableAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableAvl</b> routine instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>. In the call to <b>RtlLookupElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of the <i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLookupElementGenericTableAvl</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlisgenerictableemptyavl">RtlIsGenericTableEmptyAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>
 

 

