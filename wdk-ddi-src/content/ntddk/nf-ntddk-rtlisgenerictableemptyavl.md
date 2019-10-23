---
UID: NF:ntddk.RtlIsGenericTableEmptyAvl
title: RtlIsGenericTableEmptyAvl function (ntddk.h)
description: The RtlIsGenericTableEmptyAvl routine determines if a generic table is empty.
old-location: ifsk\rtlisgenerictableemptyavl.htm
tech.root: ifsk
ms.assetid: 9190DA2F-5530-4427-862F-00434DD9C950
ms.date: 04/16/2018
ms.keywords: RtlIsGenericTableEmptyAvl, RtlIsGenericTableEmptyAvl routine [Installable File System Drivers], ifsk.rtlisgenerictableemptyavl, ntddk/RtlIsGenericTableEmptyAvl
ms.topic: function
f1_keywords:
 - "ntddk/RtlIsGenericTableEmptyAvl"
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
req.irql: <= APC_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlIsGenericTableEmptyAvl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlIsGenericTableEmptyAvl function


## -description


The <b>RtlIsGenericTableEmptyAvl</b> routine determines if a generic table is empty. 


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <b>RtlIsGenericTableEmptyAvl</b>.


## -returns



<b>RtlIsGenericTableEmptyAvl</b> returns <b>FALSE</b> if the table contains one or more elements, <b>TRUE</b> otherwise. 




## -remarks



By default, the operating system uses splay trees to implement generic tables, but the <b>RtlIsGenericTableEmptyAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

<code>#define RTL_USE_AVL_TABLES 0</code>

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlIsGenericTableEmptyAvl</b> routine instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty">RtlIsGenericTableEmpty</a>. In the call to <b>RtlIsGenericTableEmptyAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlIsGenericTableEmptyAvl</b> must be running at ≤ APC_LEVEL if the caller-allocated memory at <i>Table</i> is pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>
 

 

