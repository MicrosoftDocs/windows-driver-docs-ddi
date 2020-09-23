---
UID: NF:ntddk.RtlNumberGenericTableElements
title: RtlNumberGenericTableElements function (ntddk.h)
description: The RtlNumberGenericTableElements routine returns the number of elements in a generic table.
old-location: ifsk\rtlnumbergenerictableelements.htm
tech.root: ifsk
ms.assetid: 7dea199f-ef98-4f7b-a3e4-de52fc23c8ef
ms.date: 04/16/2018
keywords: ["RtlNumberGenericTableElements function"]
ms.keywords: RtlNumberGenericTableElements, RtlNumberGenericTableElements routine [Installable File System Drivers], ifsk.rtlnumbergenerictableelements, ntddk/RtlNumberGenericTableElements, rtlref_f12988ba-01c3-4a34-8967-aafaf5b605f8.xml
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlNumberGenericTableElements
 - ntddk/RtlNumberGenericTableElements
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNumberGenericTableElements
---

# RtlNumberGenericTableElements function


## -description

The <b>RtlNumberGenericTableElements</b> routine returns the number of elements in a generic table.

## -parameters

### -param Table 

[in]
Pointer to the generic table (<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>.

## -returns

<b>RtlNumberGenericTableElements</b> returns the number of elements that are currently stored in the table.

## -remarks

Callers of the <i>Rtl..GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a> routine instead of <b>RtlNumberGenericTableElements</b>. In the call to <b>RtlNumberGenericTableElementsAvl</b>, the caller must pass a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlNumberGenericTableElements</b> must be running at IRQL < DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty">RtlIsGenericTableEmpty</a>