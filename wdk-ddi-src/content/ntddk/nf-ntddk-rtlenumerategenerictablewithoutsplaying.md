---
UID: NF:ntddk.RtlEnumerateGenericTableWithoutSplaying
title: RtlEnumerateGenericTableWithoutSplaying function (ntddk.h)
description: The RtlEnumerateGenericTableWithoutSplaying routine is used to enumerate the elements in a generic table.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlEnumerateGenericTableWithoutSplaying function"]
ms.keywords: RtlEnumerateGenericTableWithoutSplaying, RtlEnumerateGenericTableWithoutSplaying routine [Installable File System Drivers], ifsk.rtlenumerategenerictablewithoutsplaying, ntddk/RtlEnumerateGenericTableWithoutSplaying, rtlref_83b2461b-003b-4aee-be45-afb325b15219.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEnumerateGenericTableWithoutSplaying
 - ntddk/RtlEnumerateGenericTableWithoutSplaying
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTableWithoutSplaying
---

## -description

The **RtlEnumerateGenericTableWithoutSplaying** routine is used to enumerate the elements in a generic table.

## -parameters

### -param Table [in]

A pointer to the generic table ([RTL_GENERIC_TABLE](./ns-ntddk-_rtl_generic_table.md)). The table must have been initialized by calling [RtlInitializeGenericTable](./nf-ntddk-rtlinitializegenerictable.md).

### -param RestartKey [in, out]

An address of the element returned by the previous call to **RtlEnumerateGenericTableWithoutSplaying**. Should be set to **NULL** if the enumeration is to start at the first element in the table.

To enumerate all elements in the table, use **RtlEnumerateGenericTableWithoutSplaying** as follows:

```cpp
RestartKey = NULL;
for (ptr = RtlEnumerateGenericTableWithoutSplaying(Table, &RestartKey);
     ptr != NULL;
     ptr = RtlEnumerateGenericTableWithoutSplaying(Table, &RestartKey)) {
        // Process the element pointed to by ptr
}
```

## -returns

**RtlEnumerateGenericTableWithoutSplaying** returns a pointer to the caller-defined structure associated with the element. It returns **NULL** if *RestartKey* is **NULL** and the table has no elements or if *RestartKey* is a returned pointer and there is no next element.

## -remarks

Unlike [RtlEnumerateGenericTable](./nf-ntddk-rtlenumerategenerictable.md), **RtlEnumerateGenericTableWithoutSplaying** does not flatten the generic table by converting it from a splay tree into a sorted linked list. **RtlEnumerateGenericTableWithoutSplaying** is more efficient and multiprocessor-safe than **RtlEnumerateGenericTable**.

**RtlEnumerateGenericTableWithoutSplaying** can be called repeatedly to process the caller's data in each element of a generic table.

Callers of the *Rtl..GenericTable* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the **RtlEnumerateGenericTableWithoutSplaying** routine instead of [RtlEnumerateGenericTableWithoutSplayingAvl](./nf-ntddk-rtlenumerategenerictablewithoutsplayingavl.md). In the call to **RtlEnumerateGenericTableWithoutSplayingAvl**, the caller must pass a [RTL_AVL_TABLE](./ns-ntddk-_rtl_avl_table.md) table structure rather than [RTL_GENERIC_TABLE](./ns-ntddk-_rtl_generic_table.md).

Callers of **RtlEnumerateGenericTableWithoutSplaying** must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

[RtlEnumerateGenericTable](./nf-ntddk-rtlenumerategenerictable.md)

[RtlInitializeGenericTable](./nf-ntddk-rtlinitializegenerictable.md)

[RtlIsGenericTableEmpty](./nf-ntddk-rtlisgenerictableempty.md)

[RtlNumberGenericTableElements](./nf-ntddk-rtlnumbergenerictableelements.md)