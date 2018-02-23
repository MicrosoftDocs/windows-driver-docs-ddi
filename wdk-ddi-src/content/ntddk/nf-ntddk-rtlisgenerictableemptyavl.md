---
UID: NF:ntddk.RtlIsGenericTableEmptyAvl
title: RtlIsGenericTableEmptyAvl function
author: windows-driver-content
description: The RtlIsGenericTableEmptyAvl routine determines if a generic table is empty.
old-location: ifsk\rtlisgenerictableemptyavl.htm
old-project: ifsk
ms.assetid: 9190DA2F-5530-4427-862F-00434DD9C950
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlIsGenericTableEmptyAvl routine [Installable File System Drivers], ntddk/RtlIsGenericTableEmptyAvl, ifsk.rtlisgenerictableemptyavl, RtlIsGenericTableEmptyAvl
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlIsGenericTableEmptyAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlIsGenericTableEmptyAvl function


## -description


The <b>RtlIsGenericTableEmptyAvl</b> routine determines if a generic table is empty. 


## -syntax


````
BOOLEAN RtlIsGenericTableEmptyAvl(
  _In_ PRTL_GENERIC_TABLE Table
);
````


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <b>RtlIsGenericTableEmptyAvl</b>.


## -returns



<b>RtlIsGenericTableEmptyAvl</b> returns <b>FALSE</b> if the table contains one or more elements, <b>TRUE</b> otherwise. 




## -remarks



By default, the operating system uses splay trees to implement generic tables, but the <b>RtlIsGenericTableEmptyAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

<code>#define RTL_USE_AVL_TABLES 0</code>

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlIsGenericTableEmptyAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmpty</a>. In the call to <b>RtlIsGenericTableEmptyAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlIsGenericTableEmptyAvl</b> must be running at ≤ APC_LEVEL if the caller-allocated memory at <i>Table</i> is pageable.




## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsGenericTableEmptyAvl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

