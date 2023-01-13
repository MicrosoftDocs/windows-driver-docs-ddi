---
UID: NF:ntddk.RtlEnumerateGenericTableAvl
title: RtlEnumerateGenericTableAvl function (ntddk.h)
description: The RtlEnumerateGenericTableAvl routine is used to enumerate the elements in a generic table.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlEnumerateGenericTableAvl function"]
ms.keywords: RtlEnumerateGenericTableAvl, RtlEnumerateGenericTableAvl routine [Installable File System Drivers], ifsk.rtlenumerategenerictableavl, ntddk/RtlEnumerateGenericTableAvl
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
 - RtlEnumerateGenericTableAvl
 - ntddk/RtlEnumerateGenericTableAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTableAvl
---

## -description

The **RtlEnumerateGenericTableAvl** routine is used to enumerate the elements in a generic table.

## -parameters

### -param Table [in]

A pointer to the generic table ([RTL_AVL_TABLE](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table)). The table must have been initialized by calling [RtlInitializeGenericTableAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl).

### -param Restart [in]

Set to **TRUE** if the enumeration is to start at the first element in the table. Set to **FALSE** if resuming the enumeration from a previous call.

To enumerate all elements in the table, use **RtlEnumerateGenericTableAvl** as follows:

```cpp
for (p = RtlEnumerateGenericTableAvl ( Table, TRUE );
     p != NULL;
     p = RtlEnumerateGenericTableAvl ( Table, FALSE )) {
        // Process the element pointed to by p
}
```

## -returns

**RtlEnumerateGenericTableAvl** returns a pointer to the next element, if one exists. If there are no more elements in the table, **RtlEnumerateGenericTableAvl** returns **NULL**.

## -remarks

Callers of the *Rtl..GenericTableAvl* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

By default, the operating system uses splay trees to implement generic tables, but the **RtlEnumerateGenericTableAvl** routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the **RtlEnumerateGenericTableAvl** routine instead of [RtlEnumerateGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictable). In the call to **RtlEnumerateGenericTableAvl**, the caller must pass a [RTL_AVL_TABLE](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table) table structure rather than [RTL_GENERIC_TABLE](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table).

Callers of **RtlEnumerateGenericTableAvl** must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

[ExInitializeFastMutex](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex)

[RtlEnumerateGenericTableWithoutSplayingAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplayingavl)

[RtlInitializeGenericTableAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl)

[RtlIsGenericTableEmptyAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableemptyavl)

[RtlNumberGenericTableElementsAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl)
