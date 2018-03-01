---
UID: NF:ntddk.RtlGetElementGenericTableAvl
title: RtlGetElementGenericTableAvl function
author: windows-driver-content
description: The RtlGetElementGenericTableAvl routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element.
old-location: ifsk\rtlgetelementgenerictableavl.htm
old-project: ifsk
ms.assetid: c836dd4b-5c66-4302-9b2a-115cec418533
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlGetElementGenericTableAvl, RtlGetElementGenericTableAvl routine [Installable File System Drivers], ifsk.rtlgetelementgenerictableavl, ntddk/RtlGetElementGenericTableAvl, rtlref_c94e774b-baba-4be7-be6d-09b01544612b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available with Windows XP.
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
req.irql: Any level (See Remarks)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlGetElementGenericTableAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlGetElementGenericTableAvl function


## -description


The <b>RtlGetElementGenericTableAvl</b> routine returns a pointer to the caller-supplied data for a particular generic Adelson-Velsky/Landis (AVL) table element. 


## -syntax


````
PVOID RtlGetElementGenericTableAvl(
  _In_ PRTL_AVL_TABLE Table,
  _In_ ULONG          I
);
````


## -parameters




### -param Table [in]

Pointer to the generic AVL table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>) from which the <i>I</i>th element is to be retrieved. The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.


### -param I [in]

Index of the element selected. This value is zero-based, so the index of the last-inserted element currently in <i>Table</i> is always one less than the value returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>. 


## -returns



<b>RtlGetElementGenericTableAvl</b> returns a pointer to the caller-supplied data for the <i>I</i>th element in the generic AVL table. It returns <b>NULL</b> if the given <i>I</i> is too large or if the generic AVL table currently has no elements. 




## -remarks



<b>RtlGetElementGenericTableAvl</b> returns the <i>I</i>th element inserted in the generic AVL table. To retrieve the first element, set <i>I</i> to zero. To retrieve the last element, set <i>I</i> to (<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>(<i>Table</i>)-1). Note that if an element is deleted from the generic table, the indexes of all elements inserted after the deleted element are decremented. Thus an element's index might change over time. 

<b>RtlGetElementGenericTableAvl</b> is more efficient than <a href="..\ntddk\nf-ntddk-rtllookupelementgenerictableavl.md">RtlLookupElementGenericTableAvl</a> if the caller can supply the index of a particular element for which the caller needs access to the associated data. However, calling <b>RtlGetElementGenericTableAvl</b> repeatedly to test for such an element is less efficient than calling <b>RtlLookupElementGenericTableAvl</b> to locate it. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlGetElementGenericTableAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtlgetelementgenerictable.md">RtlGetElementGenericTable</a>. In the call to <b>RtlGetElementGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlGetElementGenericTableAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. 




## -see-also

<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictableavl.md">RtlDeleteElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictableavl.md">RtlInsertElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplayingavl.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictableavl.md">RtlLookupElementGenericTableAvl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetElementGenericTableAvl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

