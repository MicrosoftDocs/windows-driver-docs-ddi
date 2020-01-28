---
UID: NS:ntddk._RTL_AVL_TABLE
title: _RTL_AVL_TABLE (ntddk.h)
description: The RTL_AVL_TABLE structure contains file system-specific data for an Adelson-Velsky/Landis (AVL) tree.
old-location: ifsk\rtl_avl_table.htm
tech.root: ifsk
ms.assetid: 115d9489-f9f5-4dd2-bf09-33e8fd640743
ms.date: 04/16/2018
ms.keywords: "*PRTL_AVL_TABLE, PRTL_AVL_TABLE, PRTL_AVL_TABLE structure pointer [Installable File System Drivers], RTL_AVL_TABLE, RTL_AVL_TABLE structure [Installable File System Drivers], _RTL_AVL_TABLE, ifsk.rtl_avl_table, ntddk/PRTL_AVL_TABLE, ntddk/RTL_AVL_TABLE, othersystemstructures_15c34a0b-0bca-4c5f-82d9-0320ef0d33ad.xml"
f1_keywords:
 - "ntddk/RTL_AVL_TABLE"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Windows XP and later.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- RTL_AVL_TABLE
product:
- Windows
targetos: Windows
req.typenames: RTL_AVL_TABLE
---

# _RTL_AVL_TABLE structure


## -description


The RTL_AVL_TABLE structure contains file system-specific data for an Adelson-Velsky/Landis (AVL) tree. An AVL tree ensures a more balanced, shallower tree implementation than a splay tree implementation of a generic table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>). 

RTL_AVL_TABLE is opaque, so cannot be directly manipulated. Drivers must use the support routines that are described in the Remarks section to manipulate RTL_AVL_TABLE values. 


## -struct-fields




### -field BalancedRoot

Reserved for system use.


### -field OrderedPointer

Reserved for system use.


### -field WhichOrderedElement

Reserved for system use.


### -field NumberGenericTableElements

Reserved for system use.


### -field DepthOfTree

Reserved for system use.


### -field RestartKey

Reserved for system use.


### -field DeleteCount

Reserved for system use.


### -field CompareRoutine

Reserved for system use.


### -field AllocateRoutine

Reserved for system use.


### -field FreeRoutine

Reserved for system use.


### -field TableContext

Reserved for system use.


## -remarks



To initialize an AVL table package, you allocate a buffer that is at least <b>sizeof(</b>RTL_AVL_TABLE<b>) </b>bytes in size. You can then use this buffer to receive the initialized AVL table structure from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a> routine. Use the following routines to manipulate the table:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictableavl">RtlEnumerateGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablelikeadirectory">RtlEnumerateGenericTableLikeADirectory</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplayingavl">RtlEnumerateGenericTableWithoutSplayingAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictableavl">RtlGetElementGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictableavl">RtlInsertElementGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictablefullavl">RtlInsertElementGenericTableFullAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableemptyavl">RtlIsGenericTableEmptyAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictableavl">RtlLookupElementGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictablefullavl">RtlLookupElementGenericTableFullAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupfirstmatchingelementgenerictableavl">RtlLookupFirstMatchingElementGenericTableAvl</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>


</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictableavl">RtlEnumerateGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablelikeadirectory">RtlEnumerateGenericTableLikeADirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplayingavl">RtlEnumerateGenericTableWithoutSplayingAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictableavl">RtlGetElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictableavl">RtlInsertElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictablefullavl">RtlInsertElementGenericTableFullAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableemptyavl">RtlIsGenericTableEmptyAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictableavl">RtlLookupElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictablefullavl">RtlLookupElementGenericTableFullAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupfirstmatchingelementgenerictableavl">RtlLookupFirstMatchingElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>
 

 

