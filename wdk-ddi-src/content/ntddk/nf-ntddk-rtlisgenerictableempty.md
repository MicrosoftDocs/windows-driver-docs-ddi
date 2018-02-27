---
UID: NF:ntddk.RtlIsGenericTableEmpty
title: RtlIsGenericTableEmpty function
author: windows-driver-content
description: The RtlIsGenericTableEmpty routine determines if a generic table is empty.
old-location: ifsk\rtlisgenerictableempty.htm
old-project: ifsk
ms.assetid: 9d032bd1-3ee7-4044-951f-c6730a28f3a1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlIsGenericTableEmpty, RtlIsGenericTableEmpty routine [Installable File System Drivers], ifsk.rtlisgenerictableempty, ntddk/RtlIsGenericTableEmpty, rtlref_07ea645e-b497-445c-a872-34947a2f7e54.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
-	RtlIsGenericTableEmpty
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlIsGenericTableEmpty function


## -description


The <b>RtlIsGenericTableEmpty</b> routine determines if a generic table is empty. 


## -syntax


````
BOOLEAN RtlIsGenericTableEmpty(
  _In_ PRTL_GENERIC_TABLE Table
);
````


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>.


## -returns



<b>RtlIsGenericTableEmpty</b> returns <b>FALSE</b> if the table contains one or more elements, <b>TRUE</b> otherwise. 




## -remarks



By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

<code>#define RTL_USE_AVL_TABLES 0</code>

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the  <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RtlIsGenericTableEmptyAvl</a> Structure routine instead of <b>RtlIsGenericTableEmpty</b>. In the call to <a href="..\ntddk\nf-ntddk-rtlisgenerictableemptyavl.md">RtlIsGenericTableEmptyAvl</a>, the caller must pass a <b>RTL_AVL_TABLE</b> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlIsGenericTableEmpty</b> must be running at ≤ APC_LEVEL if the caller-allocated memory at <i>Table</i> is pageable.




## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsGenericTableEmpty routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

