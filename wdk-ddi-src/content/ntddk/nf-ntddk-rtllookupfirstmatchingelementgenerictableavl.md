---
UID: NF:ntddk.RtlLookupFirstMatchingElementGenericTableAvl
title: RtlLookupFirstMatchingElementGenericTableAvl function
author: windows-driver-content
description: The RtlLookupFirstMatchingElementGenericTableAvl routine finds the left-most element in the tree that matches the indicated data.
old-location: ifsk\rtllookupfirstmatchingelementgenerictableavl.htm
old-project: ifsk
ms.assetid: ff9cea5d-a93f-4d3c-b034-d2bf85484df3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlLookupFirstMatchingElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtllookupfirstmatchingelementgenerictableavl, ntddk/RtlLookupFirstMatchingElementGenericTableAvl, RtlLookupFirstMatchingElementGenericTableAvl, rtlref_60dc0941-12da-4d46-8f6d-ffbd2e394ddf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: FltKernel.h, Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	RtlLookupFirstMatchingElementGenericTableAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlLookupFirstMatchingElementGenericTableAvl function


## -description


The <b>RtlLookupFirstMatchingElementGenericTableAvl</b> routine finds the left-most element in the tree that matches the indicated data.


## -syntax


````
PVOID RtlLookupFirstMatchingElementGenericTableAvl(
  _In_  PRTL_AVL_TABLE Table,
  _In_  PVOID          Buffer,
  _Out_ PVOID          *RestartKey
);
````


## -parameters




### -param Table [in]

A pointer to the generic Adelson-Velsky/Landis (AVL) table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>).


### -param Buffer [in]

A buffer that contains the search data.


### -param RestartKey [out]

On output, contains a search context to use with an enumeration routine, such as <a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplayingavl.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>.


## -returns


The <b>RtlLookupFirstMatchingElementGenericTableAvl</b>routine returns a pointer to the matched data, or <b>NULL</b> if no match was found.



## -remarks


A tree that implements a generic table might contain several file names that differ only in case. A search algorithm can use this routine to locate the first match, without reference to case, and use an enumeration routine, such as <a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplayingavl.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>, to return each subsequent match.

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlLookupFirstMatchingElementGenericTableAvl</b>routine only works with Adelson-Velsky/Landis (AVL) trees. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. 

Callers of <b>RtlLookupFirstMatchingElementGenericTableAvl</b> must be running at &lt;= APC_LEVEL if either of the following conditions holds:
<ul>
<li>The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.</li>
<li>The caller-supplied CompareRoutine contains pageable code.</li>
</ul>


## -see-also

<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplayingavl.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLookupFirstMatchingElementGenericTableAvl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

