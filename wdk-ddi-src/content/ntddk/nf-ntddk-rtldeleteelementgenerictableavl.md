---
UID: NF:ntddk.RtlDeleteElementGenericTableAvl
title: RtlDeleteElementGenericTableAvl function (ntddk.h)
description: The RtlDeleteElementGenericTableAvl routine deletes an element from a generic table.
old-location: ifsk\rtldeleteelementgenerictableavl.htm
tech.root: ifsk
ms.assetid: 700412A3-5905-4401-BA65-C2DE1613398D
ms.date: 04/16/2018
keywords: ["RtlDeleteElementGenericTableAvl function"]
ms.keywords: RtlDeleteElementGenericTableAvl, RtlDeleteElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtldeleteelementgenerictableavl, ntddk/RtlDeleteElementGenericTableAvl
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlDeleteElementGenericTableAvl
 - ntddk/RtlDeleteElementGenericTableAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlDeleteElementGenericTableAvl
---

# RtlDeleteElementGenericTableAvl function


## -description

The <b>RtlDeleteElementGenericTableAvl</b> routine deletes an element from a generic table.

## -parameters

### -param Table 

[in]
A pointer to the generic table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.

### -param Buffer 

[in]
A pointer to a caller-allocated buffer containing a value that uniquely identifies the element to be deleted.

## -returns

<b>RtlDeleteElementGenericTableAvl</b> returns <b>TRUE</b> if the element was successfully deleted, <b>FALSE</b> otherwise.

## -remarks

<b>RtlDeleteElementGenericTableAvl</b> calls the <i>CompareRoutine</i> and <i>FreeRoutine</i> that were registered in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>. 

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlDeleteElementGenericTableAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlDeleteElementGenericTableAvl</b> routine instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>. In the call to <b>RtlDeleteElementGenericTableAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of the <i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlDeleteElementGenericTableAvl</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>FreeRoutine</i> contains pageable code. 

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictableavl">RtlInsertElementGenericTableAvl</a>

