---
UID: NF:ntddk.RtlDeleteElementGenericTable
title: RtlDeleteElementGenericTable function (ntddk.h)
description: The RtlDeleteElementGenericTable routine deletes an element from a generic table.
old-location: ifsk\rtldeleteelementgenerictable.htm
tech.root: ifsk
ms.assetid: 3bf33ebb-bdb1-487d-b10f-1f00227d7128
ms.date: 04/16/2018
keywords: ["RtlDeleteElementGenericTable function"]
ms.keywords: RtlDeleteElementGenericTable, RtlDeleteElementGenericTable routine [Installable File System Drivers], ifsk.rtldeleteelementgenerictable, ntddk/RtlDeleteElementGenericTable, rtlref_914df898-52aa-48cd-80ae-f57ffc5e60dd.xml
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
 - RtlDeleteElementGenericTable
 - ntddk/RtlDeleteElementGenericTable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDeleteElementGenericTable
---

# RtlDeleteElementGenericTable function


## -description

The <b>RtlDeleteElementGenericTable</b> routine deletes an element from a generic table.

## -parameters

### -param Table 

[in]
A pointer to the generic table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>.

### -param Buffer 

[in]
A pointer to a caller-allocated buffer containing a value that uniquely identifies the element to be deleted.

## -returns

<b>RtlDeleteElementGenericTable</b> returns <b>TRUE</b> if the element was successfully deleted, <b>FALSE</b> otherwise.

## -remarks

<b>RtlDeleteElementGenericTable</b> calls the <i>CompareRoutine</i> and <i>FreeRoutine</i> that were registered in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

`#define RTL_USE_AVL_TABLES 0`

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a> routine instead of <b>RtlDeleteElementGenericTable</b>. In the call to <b>RtlDeleteElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlDeleteElementGenericTable</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>FreeRoutine</i> contains pageable code. 

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>

