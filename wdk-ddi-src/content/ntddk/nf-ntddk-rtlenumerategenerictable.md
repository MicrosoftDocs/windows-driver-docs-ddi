---
UID: NF:ntddk.RtlEnumerateGenericTable
title: RtlEnumerateGenericTable function
author: windows-driver-content
description: The RtlEnumerateGenericTable routine is used to enumerate the elements in a generic table.
old-location: ifsk\rtlenumerategenerictable.htm
old-project: ifsk
ms.assetid: 53a5348c-71d1-4d58-82bf-1f8bf8daff90
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/RtlEnumerateGenericTable, rtlref_5fb7c196-aee1-4dcc-a39c-587472a2fbe9.xml, RtlEnumerateGenericTable routine [Installable File System Drivers], RtlEnumerateGenericTable, ifsk.rtlenumerategenerictable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlEnumerateGenericTable
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlEnumerateGenericTable function


## -description


The <b>RtlEnumerateGenericTable</b> routine is used to enumerate the elements in a generic table. 


## -syntax


````
PVOID RtlEnumerateGenericTable(
  _In_ PRTL_GENERIC_TABLE Table,
  _In_ BOOLEAN            Restart
);
````


## -parameters




### -param Table [in]

A pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>.


### -param Restart [in]

Set to <b>TRUE</b> if the enumeration is to start at the first element in the table. Set to <b>FALSE</b> if resuming the enumeration from a previous call.

To enumerate all elements in the table, use <b>RtlEnumerateGenericTable</b> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>for (p = RtlEnumerateGenericTable ( Table, TRUE );
     p != NULL;
     p = RtlEnumerateGenericTable ( Table, FALSE )) {
        // Process the element pointed to by p
}</pre>
</td>
</tr>
</table></span></div>

## -returns



<b>RtlEnumerateGenericTable</b> returns a pointer to the next element, if one exists. If there are no more elements in the table, <b>RtlEnumerateGenericTable</b> returns <b>NULL</b>. 




## -remarks



<b>RtlEnumerateGenericTable</b> flattens the generic table by converting it from a splay tree into a sorted linked list. To enumerate the table without flattening it, use <a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplaying</a>. 

Callers of the <i>Rtl..GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="..\ntddk\nf-ntddk-rtlenumerategenerictableavl.md">RtlEnumerateGenericTableAvl</a> routine instead of <b>RtlEnumerateGenericTable</b>. In the call to <b>RtlEnumerateGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlEnumerateGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElements</a>



<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmpty</a>



<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEnumerateGenericTable routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

