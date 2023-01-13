---
UID: NF:ntddk.RtlEnumerateGenericTable
title: RtlEnumerateGenericTable function (ntddk.h)
description: The RtlEnumerateGenericTable routine is used to enumerate the elements in a generic table.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlEnumerateGenericTable function"]
ms.keywords: RtlEnumerateGenericTable, RtlEnumerateGenericTable routine [Installable File System Drivers], ifsk.rtlenumerategenerictable, ntddk/RtlEnumerateGenericTable, rtlref_5fb7c196-aee1-4dcc-a39c-587472a2fbe9.xml
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
 - RtlEnumerateGenericTable
 - ntddk/RtlEnumerateGenericTable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTable
---

## -description

The **RtlEnumerateGenericTable** routine is used to enumerate the elements in a generic table.

## -parameters

### -param Table [in]

A pointer to the generic table ([**RTL_GENERIC_TABLE**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table)). The table must have been initialized by calling [RtlInitializeGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable).

### -param Restart [in]

Set to **TRUE** if the enumeration is to start at the first element in the table. Set to **FALSE** if resuming the enumeration from a previous call.

To enumerate all elements in the table, use **RtlEnumerateGenericTable** as follows:

```cpp
for (p = RtlEnumerateGenericTable ( Table, TRUE );
     p != NULL;
     p = RtlEnumerateGenericTable ( Table, FALSE )) {
        // Process the element pointed to by p
}
```

## -returns

**RtlEnumerateGenericTable** returns a pointer to the next element, if one exists. If there are no more elements in the table, **RtlEnumerateGenericTable** returns **NULL**.

## -remarks

**RtlEnumerateGenericTable** flattens the generic table by converting it from a splay tree into a sorted linked list. To enumerate the table without flattening it, use [RtlEnumerateGenericTableWithoutSplaying](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying).

Callers of the *Rtl..GenericTable* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the [RtlEnumerateGenericTableAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictableavl) routine instead of **RtlEnumerateGenericTable**. In the call to **RtlEnumerateGenericTableAvl**, the caller must pass a [RTL_AVL_TABLE](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table) table structure rather than [**RTL_GENERIC_TABLE**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table).

Callers of **RtlEnumerateGenericTable** must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

[ExInitializeFastMutex](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex)

[RtlEnumerateGenericTableWithoutSplaying](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying)

[RtlInitializeGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable)

[RtlIsGenericTableEmpty](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty)

[RtlNumberGenericTableElements](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements)
