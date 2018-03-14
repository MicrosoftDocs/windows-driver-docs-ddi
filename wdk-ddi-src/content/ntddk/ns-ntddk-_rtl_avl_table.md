---
UID: NS:ntddk._RTL_AVL_TABLE
title: "_RTL_AVL_TABLE"
author: windows-driver-content
description: The RTL_AVL_TABLE structure contains file system-specific data for an Adelson-Velsky/Landis (AVL) tree.
old-location: ifsk\rtl_avl_table.htm
old-project: ifsk
ms.assetid: 115d9489-f9f5-4dd2-bf09-33e8fd640743
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PRTL_AVL_TABLE, PRTL_AVL_TABLE, PRTL_AVL_TABLE structure pointer [Installable File System Drivers], RTL_AVL_TABLE, RTL_AVL_TABLE structure [Installable File System Drivers], _RTL_AVL_TABLE, ifsk.rtl_avl_table, ntddk/PRTL_AVL_TABLE, ntddk/RTL_AVL_TABLE, othersystemstructures_15c34a0b-0bca-4c5f-82d9-0320ef0d33ad.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RTL_AVL_TABLE
product: Windows
targetos: Windows
req.typenames: RTL_AVL_TABLE
---

# _RTL_AVL_TABLE structure


## -description


The RTL_AVL_TABLE structure contains file system-specific data for an Adelson-Velsky/Landis (AVL) tree. An AVL tree ensures a more balanced, shallower tree implementation than a splay tree implementation of a generic table (<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>). 

RTL_AVL_TABLE is opaque, so cannot be directly manipulated. Drivers must use the support routines that are described in the Remarks section to manipulate RTL_AVL_TABLE values. 


## -syntax


````
typedef struct _RTL_AVL_TABLE {
  RTL_BALANCED_LINKS        BalancedRoot;
  PVOID                     OrderedPointer;
  ULONG                     WhichOrderedElement;
  ULONG                     NumberGenericTableElements;
  ULONG                     DepthOfTree;
  PRTL_BALANCED_LINKS       RestartKey;
  ULONG                     DeleteCount;
  PRTL_AVL_COMPARE_ROUTINE  CompareRoutine;
  PRTL_AVL_ALLOCATE_ROUTINE AllocateRoutine;
  PRTL_AVL_FREE_ROUTINE     FreeRoutine;
  PVOID                     TableContext;
} RTL_AVL_TABLE, *PRTL_AVL_TABLE;
````


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



To initialize an AVL table package, you allocate a buffer that is at least <b>sizeof(</b>RTL_AVL_TABLE<b>) </b>bytes in size. You can then use this buffer to receive the initialized AVL table structure from a call to the <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTableAvl</a> routine. Use the following routines to manipulate the table:

<ul>
<li>

<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlenumerategenerictable.md">RtlEnumerateGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablelikeadirectory.md">RtlEnumerateGenericTableLikeADirectory</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlgetelementgenerictableavl.md">RtlGetElementGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictable.md">RtlInsertElementGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictablefullavl.md">RtlInsertElementGenericTableFullAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmptyAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictablefullavl.md">RtlLookupElementGenericTableFullAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtllookupfirstmatchingelementgenerictableavl.md">RtlLookupFirstMatchingElementGenericTableAvl</a>


</li>
<li>

<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElementsAvl</a>


</li>
</ul>



## -see-also

<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictablefullavl.md">RtlInsertElementGenericTableFullAvl</a>



<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElementsAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictable.md">RtlInsertElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablelikeadirectory.md">RtlEnumerateGenericTableLikeADirectory</a>



<a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>



<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmptyAvl</a>



<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictablefullavl.md">RtlLookupElementGenericTableFullAvl</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplayingAvl</a>



<a href="..\ntddk\nf-ntddk-rtlgetelementgenerictableavl.md">RtlGetElementGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictable.md">RtlEnumerateGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtllookupfirstmatchingelementgenerictableavl.md">RtlLookupFirstMatchingElementGenericTableAvl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RTL_AVL_TABLE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

