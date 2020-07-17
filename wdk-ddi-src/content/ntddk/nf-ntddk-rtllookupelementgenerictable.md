---
UID: NF:ntddk.RtlLookupElementGenericTable
title: RtlLookupElementGenericTable function (ntddk.h)
description: The RtlLookupElementGenericTable routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictable.htm
tech.root: ifsk
ms.assetid: 9182084b-ea11-48e4-acb5-06a8375d05bf
ms.date: 04/16/2018
keywords: ["RtlLookupElementGenericTable function"]
ms.keywords: RtlLookupElementGenericTable, RtlLookupElementGenericTable routine [Installable File System Drivers], ifsk.rtllookupelementgenerictable, ntddk/RtlLookupElementGenericTable, rtlref_609e7ba3-35a1-40e8-9e94-f16605e52155.xml
f1_keywords:
 - "ntddk/RtlLookupElementGenericTable"
 - "RtlLookupElementGenericTable"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlLookupElementGenericTable
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLookupElementGenericTable function

## -description

The **RtlLookupElementGenericTable** routine searches a generic table for an element that matches the specified data.

## -parameters

### -param Table

Pointer to the generic table ([RTL_GENERIC_TABLE](ns-ntddk-_rtl_generic_table.md)). The table must have been initialized by calling **RtlInitializeGenericTable**.

### -param Buffer

A buffer of search data to pass to the *CompareRoutine* that was registered when [RtlInitializeGenericTable](nf-ntddk-rtlinitializegenerictable.md) initialized the generic table. For more information, see the description of **RtlInitializeGenericTable**.

## -returns

**RtlLookupElementGenericTable** returns a pointer to the caller-supplied data for the desired element in the generic table. It returns **NULL** if the generic table currently has no elements or if no matching element is found.

## -remarks

If a matching element is found, **RtlLookupElementGenericTable** rebalances the generic table's splay tree.

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *ntddk.h*:

```
#define RTL_USE_AVL_TABLES 0
```

If you do not define RTL_USE_AVL_TABLES as specified above, you must use the AVL form of the generic table routines. For example, use the [RtlLookupElementGenericTableAvl](nf-ntddk-rtllookupelementgenerictableavl.md) routine instead of **RtlLookupElementGenericTable**. In the call to **RtlLookupElementGenericTableAvl**, the caller must pass a [RTL_AVL_TABLE](ns-ntddk-_rtl_avl_table.md) table structure rather than [RTL_GENERIC_TABLE](ns-ntddk-_rtl_generic_table.md).

Callers of **RtlLookupElementGenericTable** must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

* The caller-allocated memory at *Table* or at *Buffer* is pageable.

* The caller-supplied *CompareRoutine* contains pageable code.

Otherwise, callers of **RtlLookupElementGenericTable** can run at IRQL <= DISPATCH_LEVEL when using non-paged memory or code.

## -see-also

[RTL_AVL_TABLE](ns-ntddk-_rtl_avl_table.md)

[RTL_GENERIC_TABLE](ns-ntddk-_rtl_generic_table.md)

[RtlInitializeGenericTable](nf-ntddk-rtlinitializegenerictable.md)

[RtlIsGenericTableEmpty](nf-ntddk-rtlisgenerictableempty.md)

[RtlNumberGenericTableElements](nf-ntddk-rtlnumbergenerictableelements.md)
