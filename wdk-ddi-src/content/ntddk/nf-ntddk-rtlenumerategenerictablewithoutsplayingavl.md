---
UID: NF:ntddk.RtlEnumerateGenericTableWithoutSplayingAvl
title: RtlEnumerateGenericTableWithoutSplayingAvl function (ntddk.h)
description: The RtlEnumerateGenericTableWithoutSplayingAvl routine is used to enumerate the elements in a generic table.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlEnumerateGenericTableWithoutSplayingAvl function"]
ms.keywords: RtlEnumerateGenericTableWithoutSplayingAvl, RtlEnumerateGenericTableWithoutSplayingAvl routine [Installable File System Drivers], ifsk.rtlenumerategenerictablewithoutsplayingavl, ntddk/RtlEnumerateGenericTableWithoutSplayingAvl
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
 - RtlEnumerateGenericTableWithoutSplayingAvl
 - ntddk/RtlEnumerateGenericTableWithoutSplayingAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTableWithoutSplayingAvl
---

## -description

The **RtlEnumerateGenericTableWithoutSplayingAvl** routine is used to enumerate the elements in a generic table.

## -parameters

### -param Table [in]

A pointer to the generic table ([RTL_AVL_TABLE](./ns-ntddk-_rtl_avl_table.md)). The table must have been initialized by calling [RtlInitializeGenericTableAvl](./nf-ntddk-rtlinitializegenerictableavl.md).

### -param RestartKey [in, out]

An address of the element returned by the previous call to **RtlEnumerateGenericTableWithoutSplayingAvl**. Should be set to **NULL** if the enumeration is to start at the first element in the table.

To enumerate all elements in the table, use **RtlEnumerateGenericTableWithoutSplayingAvl** as follows:

```cpp
RestartKey = NULL;
for (ptr = RtlEnumerateGenericTableWithoutSplayingAvl(Table, &RestartKey);
     ptr != NULL;
     ptr = RtlEnumerateGenericTableWithoutSplayingAvl(Table, &RestartKey)) {
        // Process the element pointed to by ptr
}
```

## -returns

**RtlEnumerateGenericTableWithoutSplayingAvl** returns a pointer to the caller-defined structure associated with the element. It returns **NULL** if *RestartKey* is **NULL** and the table has no elements or if *RestartKey* is a returned pointer and there is no next element.

## -remarks

The **RtlEnumerateGenericTableWithoutSplayingAvl** routine does not actually work with a splay tree but provides an analogous named routine to **RtlEnumerateGenericTableWithoutSplayingAvl**.

**RtlEnumerateGenericTableWithoutSplayingAvl** can be called repeatedly to process the caller's data in each element of a generic table.

By default, the operating system uses splay trees to implement generic tables, but the [RtlLookupElementGenericTableFullAvl](./nf-ntddk-rtllookupelementgenerictablefullavl.md) routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the **RtlEnumerateGenericTableWithoutSplayingAvl** routine instead of [RtlEnumerateGenericTableWithoutSplaying](./nf-ntddk-rtlenumerategenerictablewithoutsplaying.md). In the call to **RtlEnumerateGenericTableWithoutSplayingAvl**, the caller must pass a [RTL_AVL_TABLE](./ns-ntddk-_rtl_avl_table.md) table structure rather than [RTL_GENERIC_TABLE](./ns-ntddk-_rtl_generic_table.md).

Callers of the* Rtl..GenericTableAvl* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

Callers of **RtlEnumerateGenericTableWithoutSplayingAvl** must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

[RtlEnumerateGenericTableAvl](./nf-ntddk-rtlenumerategenerictableavl.md)

[RtlInitializeGenericTableAvl](./nf-ntddk-rtlinitializegenerictableavl.md)

[RtlIsGenericTableEmptyAvl](./nf-ntddk-rtlisgenerictableemptyavl.md)

[RtlNumberGenericTableElementsAvl](./nf-ntddk-rtlnumbergenerictableelementsavl.md)