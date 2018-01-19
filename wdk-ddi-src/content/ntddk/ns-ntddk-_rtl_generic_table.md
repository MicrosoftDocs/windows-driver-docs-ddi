---
UID: NS:ntddk._RTL_GENERIC_TABLE
title: _RTL_GENERIC_TABLE
author: windows-driver-content
description: The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree.
old-location: ifsk\rtl_generic_table.htm
old-project: ifsk
ms.assetid: 0e5dba1b-8b0d-470a-8ead-4c022e9da7fe
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _RTL_GENERIC_TABLE, RTL_GENERIC_TABLE, *PRTL_GENERIC_TABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RTL_GENERIC_TABLE
req.alt-loc: ntddk.h
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
req.typenames: RTL_GENERIC_TABLE
---

# _RTL_GENERIC_TABLE structure



## -description
The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree. 

RTL_GENERIC_TABLE is opaque and not directly manipulated. Drivers must use the support routines that are described in the Remarks section to manipulate RTL_GENERIC_TABLE values. 



## -syntax

````
typedef struct _RTL_GENERIC_TABLE {
  PRTL_SPLAY_LINKS              TableRoot;
  LIST_ENTRY                    InsertOrderList;
  PLIST_ENTRY                   OrderedPointer;
  ULONG                         WhichOrderedElement;
  ULONG                         NumberGenericTableElements;
  PRTL_GENERIC_COMPARE_ROUTINE  CompareRoutine;
  PRTL_GENERIC_ALLOCATE_ROUTINE AllocateRoutine;
  PRTL_GENERIC_FREE_ROUTINE     FreeRoutine;
  PVOID                         TableContext;
} RTL_GENERIC_TABLE, *PRTL_GENERIC_TABLE;
````


## -struct-fields

### -field TableRoot

Reserved for system use.


### -field InsertOrderList

Reserved for system use.


### -field OrderedPointer

Reserved for system use.


### -field WhichOrderedElement

Reserved for system use.


### -field NumberGenericTableElements

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
To initialize a generic table package, you allocate a buffer that is at least <b>sizeof(</b>RTL_GENERIC_TABLE<b>) </b>bytes in size to receive the initialized generic table structure from a call to the <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a> routine. You can use the following routines to manipulate the table:


<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictable.md">RtlEnumerateGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="..\ntddk\nf-ntddk-rtlgetelementgenerictable.md">RtlGetElementGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictable.md">RtlInsertElementGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictablefullavl.md">RtlInsertElementGenericTableFull</a>



<a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmpty</a>



<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTable</a>



<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictablefullavl.md">RtlLookupElementGenericTableFull</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElements</a>



## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlenumerategenerictable.md">RtlEnumerateGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplaying</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlgetelementgenerictable.md">RtlGetElementGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictable.md">RtlInsertElementGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictablefullavl.md">RtlInsertElementGenericTableFull</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmpty</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictablefullavl.md">RtlLookupElementGenericTableFull</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelements.md">RtlNumberGenericTableElements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RTL_GENERIC_TABLE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

