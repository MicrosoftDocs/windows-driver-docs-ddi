---
UID: NF:ntddk.RtlInsertElementGenericTableFullAvl
title: RtlInsertElementGenericTableFullAvl function (ntddk.h)
description: The RtlInsertElementGenericTableFullAvl routine adds a new entry to a generic table.
old-location: ifsk\rtlinsertelementgenerictablefullavl.htm
tech.root: ifsk
ms.assetid: c7d346ab-6990-4636-bafd-2e448a937f3b
ms.date: 04/16/2018
keywords: ["RtlInsertElementGenericTableFullAvl function"]
ms.keywords: RtlInsertElementGenericTableFullAvl, RtlInsertElementGenericTableFullAvl routine [Installable File System Drivers], ifsk.rtlinsertelementgenerictablefullavl, ntddk/RtlInsertElementGenericTableFullAvl, rtlref_425ca8ff-1fa8-4bdf-84ea-a8935cf0df59.xml
f1_keywords:
 - "ntddk/RtlInsertElementGenericTableFullAvl"
 - "RtlInsertElementGenericTableFullAvl"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlInsertElementGenericTableFullAvl
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInsertElementGenericTableFullAvl function


## -description


The <b>RtlInsertElementGenericTableFullAvl</b> routine adds a new entry to a generic table. 


## -parameters




### -param Table [in]

Pointer to a generic Adelson-Velsky/Landis (AVL) table (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>) that was initialized by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>.


### -param Buffer [in]

A caller-allocated buffer that contains the user data to copy into the new element. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>. 


### -param BufferSize [in]

Size in bytes of data in <i>Buffer.</i>


### -param NewElement [out, optional]

On output, a value of <b>TRUE</b> means the insertion of the new element in the generic table was successful. A value of <b>FALSE</b> means the insertion failed.


### -param NodeOrParent [in]

The search result of a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictablefullavl">RtlLookupElementGenericTableFullAvl</a>. This value indicates to the <b>RtlInsertElementGenericTableFullAvl</b> routine whether the tree is currently empty, or if not empty, whether to insert the new entry to the left or the right of the parent entry. The <i>SearchResult</i> parameter can have any of the following values:





#### TableEmptyTree

The tree was empty. The contents of <i>NodeOrParent</i> has <i>not</i> been altered.



#### TableFoundNode

The <b>RtlInsertElementGenericTableFullAvl</b> routine found a table entry whose key matches the data in <i>Buffer</i>. <i>NodeOrParent</i> contains a pointer to the matched entry.



#### TableInsertAsLeft

The <b>RtlInsertElementGenericTableFullAvl</b> routine did <i>not</i> find a table entry whose key matches the data in <i>Buffer</i>. If the entry that <b>RtlInsertElementGenericTableFullAvl</b> searched for were in the table, it would be the left child of the entry that <i>NodeOrParent</i> points to.



#### TableInsertAsRight

The <b>RtlInsertElementGenericTableFullAvl</b> routine did <i>not</i> find a table entry whose key matches the data in <i>Buffer</i>. If the entry that <b>RtlInsertElementGenericTableFullAvl</b> searched for were in the table, it would be the right child of the entry that <i>NodeOrParent</i> points to.


### -param SearchResult [in]

A pointer to a table entry. If the <b>RtlInsertElementGenericTableFullAvl</b> routine matches an entry, <i>NodeOrParent</i> points to the matched entry. If the <b>RtlInsertElementGenericTableFullAvl</b> routine fails to find a match, <i>NodeOrParent</i> points to the entry that would be the parent of the entry that <b>RtlInsertElementGenericTableFullAvl</b> routine was searching for.


## -returns



<b>RtlInsertElementGenericTableFullAvl</b> returns a pointer to the user data for the newly inserted entry, or the user data for a matching entry that is already in the generic table. If no matching entry is found, but <b>RtlInsertElementGenericTableFullAvl</b> cannot insert the new entry (for example, because the <i>AllocateRoutine</i> fails), <b>RtlInsertElementGenericTableFullAvl</b> returns <b>NULL</b>. 




## -remarks



To insert an entry, <b>RtlInsertElementGenericTableFullAvl</b> calls the <i>CompareRoutine</i> and <i>AllocateRoutine</i> that were registered when the generic table was initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a>. After inserting the new entry, <b>RtlInsertElementGenericTableFullAvl</b> rebalances the AVL link tree.

When a new entry is inserted into the table, its data is copied from <i>Buffer</i> into the new entry. Thus the pointer returned by <b>RtlInsertElementGenericTableFullAvl</b> is never equal to <i>Buffer</i>. 

If the caller's <i>CompareRoutine</i> returns <b>GenericEqual</b>, the data at <i>Buffer</i> is assumed to duplicate the data for an existing entry in the generic table. In this case, <b>RtlInsertElementGenericTableFullAvl</b> does not add the new entry (and thus does not call the <i>AllocateRoutine</i>), because a generic table cannot have duplicate entries.

If a matching entry already exists in the generic table, <b>RtlInsertElementGenericTableFullAvl</b> returns a pointer to the existing entry's data and sets <i>NewElement</i> to <b>FALSE</b>. 

If there is no matching entry in the table already,<b>RtlInsertElementGenericTableFullAvl</b> routine allocates sufficient space for the user data of new entry (<i>BufferSize</i>) plus the links associated with the new entry. Thus the total number of bytes will be at least <i>BufferSize</i> + <b>sizeof</b>(BALANCED_LINKS). Caller should not use the first <b>sizeof</b>(BALANCED_LINKS) bytes of the memory that the <i>AllocateRoutine</i>allocates.

Callers of the<i>Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlInsertElementGenericTableFullAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlInsertElementGenericTableFullAvl</b> routine instead of <b>RtlInsertElementGenericTableFull</b>. In the call to <b>RtlInsertElementGenericTableFullAvl</b>, the caller must pass a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlInsertElementGenericTableFullAvl</b> must be running at IRQL < DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>AllocateRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>
 

 

