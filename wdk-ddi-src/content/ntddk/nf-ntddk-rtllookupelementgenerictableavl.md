---
UID: NF:ntddk.RtlLookupElementGenericTableAvl
title: RtlLookupElementGenericTableAvl function
author: windows-driver-content
description: The RtlLookupElementGenericTableAvl routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictableavl.htm
old-project: ifsk
ms.assetid: 7A10B5E7-293E-4E28-BAB8-E189891A851A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, E, G, L, R, RtlLookupElementGenericTableAvl, RtlLookupElementGenericTableAvl routine [Installable File System Drivers], T, a, b, c, e, i, ifsk.rtllookupelementgenerictableavl, k, l, m, n, ntddk/RtlLookupElementGenericTableAvl, o, p, r, t, u, v"
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
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlLookupElementGenericTableAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlLookupElementGenericTableAvl function


## -description


The <b>RtlLookupElementGenericTableAvl</b> routine searches a generic table for an element that matches the specified data.


## -syntax


````
PVOID RtlLookupElementGenericTableAvl(
  _In_ PRTL_AVL_TABLE Table,
  _In_ PVOID          Buffer
);
````


## -parameters




### -param Table [in]

Pointer to the generic Adelson-Velsky/Landis (AVL) table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.


### -param Buffer [in]

A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTableAvl</b>.


## -returns



<b>RtlLookupElementGenericTableAvl</b> returns a pointer to the user data that is associated with the matching element in the generic table, or <b>NULL</b> if the generic table currently has no elements or if no matching element is found.




## -remarks



By default, the operating system uses splay trees to implement generic tables, but the <b>RtlLookupElementGenericTableAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTable</a>. In the call to <b>RtlLookupElementGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of the <i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLookupElementGenericTableAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also

<a href="..\ntddk\nf-ntddk-rtlisgenerictableemptyavl.md">RtlIsGenericTableEmptyAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLookupElementGenericTableAvl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

