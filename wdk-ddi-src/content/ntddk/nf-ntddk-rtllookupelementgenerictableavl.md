---
UID: NF:ntddk.RtlLookupElementGenericTableAvl
title: RtlLookupElementGenericTableAvl function (ntddk.h)
description: The RtlLookupElementGenericTableAvl routine searches a generic table for an element that matches the specified data.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlLookupElementGenericTableAvl function"]
ms.keywords: RtlLookupElementGenericTableAvl, RtlLookupElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtllookupelementgenerictableavl, ntddk/RtlLookupElementGenericTableAvl
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
req.irql: IRQL < DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlLookupElementGenericTableAvl
 - ntddk/RtlLookupElementGenericTableAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlLookupElementGenericTableAvl
---

## -description

The **RtlLookupElementGenericTableAvl** routine searches a generic table for an element that matches the specified data.

## -parameters

### -param Table [in]

Pointer to the generic Adelson-Velsky/Landis (AVL) table ([**RTL_AVL_TABLE**](./ns-ntddk-_rtl_avl_table.md)). The table must have been initialized by calling [RtlInitializeGenericTableAvl](./nf-ntddk-rtlinitializegenerictableavl.md).

### -param Buffer [in]

A buffer of search data to pass to the *CompareRoutine* that was registered when [RtlInitializeGenericTableAvl](./nf-ntddk-rtlinitializegenerictableavl.md) initialized the generic table. For more information, see the description of **RtlInitializeGenericTableAvl**.

## -returns

**RtlLookupElementGenericTableAvl** returns a pointer to the user data that is associated with the matching element in the generic table, or **NULL** if the generic table currently has no elements or if no matching element is found.

## -remarks

By default, the operating system uses splay trees to implement generic tables, but the **RtlLookupElementGenericTableAvl** routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the **RtlLookupElementGenericTableAvl** routine instead of [RtlLookupElementGenericTable](./nf-ntddk-rtllookupelementgenerictable.md). In the call to **RtlLookupElementGenericTableAvl**, the caller must pass a [**RTL_AVL_TABLE**](./ns-ntddk-_rtl_avl_table.md) table structure rather than [**RTL_GENERIC_TABLE**](./ns-ntddk-_rtl_generic_table.md).

Callers of the *Rtl..GenericTableAvl* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

Callers of **RtlLookupElementGenericTableAvl** must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

- The caller-allocated memory at *Table* or at *Buffer* is pageable.

- The caller-supplied *CompareRoutine* contains pageable code.

## -see-also

[RtlInitializeGenericTableAvl](./nf-ntddk-rtlinitializegenerictableavl.md)

[RtlIsGenericTableEmptyAvl](./nf-ntddk-rtlisgenerictableemptyavl.md)

[RtlNumberGenericTableElementsAvl](./nf-ntddk-rtlnumbergenerictableelementsavl.md)