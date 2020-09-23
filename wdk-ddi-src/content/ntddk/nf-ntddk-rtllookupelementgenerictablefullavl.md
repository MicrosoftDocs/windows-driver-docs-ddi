---
UID: NF:ntddk.RtlLookupElementGenericTableFullAvl
title: RtlLookupElementGenericTableFullAvl function (ntddk.h)
description: The RtlLookupElementGenericTableFullAvl routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictablefullavl.htm
tech.root: ifsk
ms.assetid: fddb2e23-ddb3-48bc-a94e-0ca9a8580b78
ms.date: 04/16/2018
keywords: ["RtlLookupElementGenericTableFullAvl function"]
ms.keywords: RtlLookupElementGenericTableFullAvl, RtlLookupElementGenericTableFullAvl routine [Installable File System Drivers], ifsk.rtllookupelementgenerictablefullavl, ntddk/RtlLookupElementGenericTableFullAvl, rtlref_12eb0cb8-ea58-45a8-a88b-ceddc5af12c6.xml
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlLookupElementGenericTableFullAvl
 - ntddk/RtlLookupElementGenericTableFullAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlLookupElementGenericTableFullAvl
---

# RtlLookupElementGenericTableFullAvl function


## -description

The <b>RtlLookupElementGenericTableFullAvl</b> routine searches a generic table for an element that matches the specified data.

## -parameters

### -param Table 

[in]
Pointer to the generic Adelson-Velsky/Landis (AVL) table (<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.

### -param Buffer 

[in]
A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTableAvl</b>.

### -param NodeOrParent 

[out]
On output, a value that describes the relationship of the <i>NodeOrParent</i> with the table entry (node) that <b>RtlLookupElementGenericTableFullAvl</b> is searching for. The <i>SearchResult</i> parameter can have any of the following values:





#### TableEmptyTree

The tree was empty. The contents of <i>NodeOrParent</i> has <i>not</i> been altered.



#### TableFoundNode

The <b>RtlLookupElementGenericTableFullAvl</b> routine found a table entry whose key matches the data in <i>Buffer</i>. <i>NodeOrParent</i> contains a pointer to the matched entry.



#### TableInsertAsLeft

The <b>RtlLookupElementGenericTableFullAvl</b> routine did <i>not</i>find a table entry whose key matches the data in <i>Buffer</i>. I<i>not</i>f the entry that <b>RtlLookupElementGenericTableFullAvl</b> searched for were in the table, it would be the left child of the entry that <i>NodeOrParent</i> points to.



#### TableInsertAsRight

The <b>RtlLookupElementGenericTableFullAvl</b> routine did <i>not</i>find a table entry whose key matches the data in <i>Buffer</i>. If the entry that <b>RtlLookupElementGenericTableFullAvl</b> searched for were in the table, it would be the right child of the entry that <i>NodeOrParent</i> points to.

### -param SearchResult 

[out]
A pointer to a table entry. If the <b>RtlLookupElementGenericTableFullAvl</b> routine matches an entry, <i>NodeOrParent</i>points to the matched entry. If the <b>RtlLookupElementGenericTableFullAvl</b> routine fails to find a match, <i>NodeOrParent</i> points to the entry that would be the parent of the entry that <b>RtlLookupElementGenericTableFullAvl</b> routine was searching for.

## -returns

<b>RtlLookupElementGenericTableFullAvl</b> returns a pointer to the user data that is associated with the matching element in the generic table, or <b>NULL</b> if the generic table currently has no elements or if no matching element is found.

## -remarks

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlLookupElementGenericTableFullAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableFullAvl</b> routine instead of <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>. In the call to <b>RtlLookupElementGenericTableFullAvl</b>, the caller must pass a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLookupElementGenericTableFullAvl</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> contains pageable code. 

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableemptyavl">RtlIsGenericTableEmptyAvl</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>