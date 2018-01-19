---
UID: NF:ntddk.RtlDeleteElementGenericTableAvl
title: RtlDeleteElementGenericTableAvl function
author: windows-driver-content
description: The RtlDeleteElementGenericTableAvl routine deletes an element from a generic table.
old-location: ifsk\rtldeleteelementgenerictableavl.htm
old-project: ifsk
ms.assetid: 700412A3-5905-4401-BA65-C2DE1613398D
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlDeleteElementGenericTableAvl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlDeleteElementGenericTableAvl
req.alt-loc: NtosKrnl.exe
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlDeleteElementGenericTableAvl function



## -description
The <b>RtlDeleteElementGenericTableAvl</b> routine deletes an element from a generic table. 



## -syntax

````
BOOLEAN RtlDeleteElementGenericTableAvl(
  _In_ PRTL_AVL_TABLE Table,
  _In_ PVOID          Buffer
);
````


## -parameters

### -param Table [in]

A pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.


### -param Buffer [in]

A pointer to a caller-allocated buffer containing a value that uniquely identifies the element to be deleted.


## -returns
<b>RtlDeleteElementGenericTableAvl</b> returns <b>TRUE</b> if the element was successfully deleted, <b>FALSE</b> otherwise.


## -remarks
<b>RtlDeleteElementGenericTableAvl</b> calls the <i>CompareRoutine</i> and <i>FreeRoutine</i> that were registered in the call to <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>. 

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlDeleteElementGenericTableAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlDeleteElementGenericTableAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTable</a>. In the call to <b>RtlDeleteElementGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of the <i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlDeleteElementGenericTableAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

The caller-supplied <i>CompareRoutine</i> or <i>FreeRoutine</i> contains pageable code. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictableavl.md">RtlInsertElementGenericTableAvl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDeleteElementGenericTableAvl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

