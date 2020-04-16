---
UID: NS:ntddk._RTL_GENERIC_TABLE
title: _RTL_GENERIC_TABLE (ntddk.h)
description: The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree.
old-location: ifsk\rtl_generic_table.htm
tech.root: ifsk
ms.assetid: 0e5dba1b-8b0d-470a-8ead-4c022e9da7fe
ms.date: 04/16/2018
keywords: ["_RTL_GENERIC_TABLE structure"]
ms.keywords: "*PRTL_GENERIC_TABLE, PRTL_GENERIC_TABLE, PRTL_GENERIC_TABLE structure pointer [Installable File System Drivers], RTL_GENERIC_TABLE, RTL_GENERIC_TABLE structure [Installable File System Drivers], _RTL_GENERIC_TABLE, ifsk.rtl_generic_table, ntddk/PRTL_GENERIC_TABLE, ntddk/RTL_GENERIC_TABLE, othersystemstructures_ce9bd546-d224-429d-8835-be3d5ecb1a52.xml"
f1_keywords:
 - "ntddk/RTL_GENERIC_TABLE"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Windows 2000 and later.
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
- RTL_GENERIC_TABLE
product:
- Windows
targetos: Windows
req.typenames: RTL_GENERIC_TABLE
---

# _RTL_GENERIC_TABLE structure


## -description


The RTL_GENERIC_TABLE structure contains file system-specific data for a splay tree. 

RTL_GENERIC_TABLE is opaque and not directly manipulated. Drivers must use the support routines that are described in the Remarks section to manipulate RTL_GENERIC_TABLE values. 


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



To initialize a generic table package, you allocate a buffer that is at least <b>sizeof(</b>RTL_GENERIC_TABLE<b>) </b>bytes in size to receive the initialized generic table structure from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a> routine. You can use the following routines to manipulate the table:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictable">RtlEnumerateGenericTable</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictable">RtlGetElementGenericTable</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictablefullavl">RtlInsertElementGenericTableFull</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty">RtlIsGenericTableEmpty</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictablefullavl">RtlLookupElementGenericTableFull</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>


</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictable">RtlEnumerateGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictable">RtlGetElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictablefullavl">RtlInsertElementGenericTableFull</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlisgenerictableempty">RtlIsGenericTableEmpty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictablefullavl">RtlLookupElementGenericTableFull</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>
 

 

