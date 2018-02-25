---
UID: NF:ntddk.RtlDeleteElementGenericTable
title: RtlDeleteElementGenericTable function
author: windows-driver-content
description: The RtlDeleteElementGenericTable routine deletes an element from a generic table.
old-location: ifsk\rtldeleteelementgenerictable.htm
old-project: ifsk
ms.assetid: 3bf33ebb-bdb1-487d-b10f-1f00227d7128
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, E, G, R, RtlDeleteElementGenericTable, RtlDeleteElementGenericTable routine [Installable File System Drivers], T, a, b, c, e, i, ifsk.rtldeleteelementgenerictable, l, m, n, ntddk/RtlDeleteElementGenericTable, r, rtlref_914df898-52aa-48cd-80ae-f57ffc5e60dd.xml, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlDeleteElementGenericTable
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlDeleteElementGenericTable function


## -description


The <b>RtlDeleteElementGenericTable</b> routine deletes an element from a generic table. 


## -syntax


````
BOOLEAN RtlDeleteElementGenericTable(
  _In_ PRTL_GENERIC_TABLE Table,
  _In_ PVOID              Buffer
);
````


## -parameters




### -param Table [in]

A pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>.


### -param Buffer [in]

A pointer to a caller-allocated buffer containing a value that uniquely identifies the element to be deleted.


## -returns



<b>RtlDeleteElementGenericTable</b> returns <b>TRUE</b> if the element was successfully deleted, <b>FALSE</b> otherwise.




## -remarks



<b>RtlDeleteElementGenericTable</b> calls the <i>CompareRoutine</i> and <i>FreeRoutine</i> that were registered in the call to <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictableavl.md">RtlDeleteElementGenericTableAvl</a> routine instead of <b>RtlDeleteElementGenericTable</b>. In the call to <b>RtlDeleteElementGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlDeleteElementGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>FreeRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictable.md">RtlInsertElementGenericTable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDeleteElementGenericTable routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

