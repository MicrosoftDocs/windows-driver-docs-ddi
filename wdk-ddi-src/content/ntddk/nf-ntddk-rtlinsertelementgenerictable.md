---
UID: NF:ntddk.RtlInsertElementGenericTable
title: RtlInsertElementGenericTable function
author: windows-driver-content
description: The RtlInsertElementGenericTable routine adds a new element to a generic table.
old-location: ifsk\rtlinsertelementgenerictable.htm
old-project: ifsk
ms.assetid: 2554a212-edc0-4641-98bb-2db36ff0266f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlInsertElementGenericTable, RtlInsertElementGenericTable routine [Installable File System Drivers], ifsk.rtlinsertelementgenerictable, ntddk/RtlInsertElementGenericTable, rtlref_62ab1129-906f-4ef7-b0d1-bec4bf6fce62.xml
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
req.irql: "< DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInsertElementGenericTable
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlInsertElementGenericTable function


## -description


The <b>RtlInsertElementGenericTable</b> routine adds a new element to a generic table. 


## -parameters




### -param Table [in]

Pointer to the generic table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>.


### -param Buffer [in]

Pointer to a caller-allocated buffer containing data to be copied into the new element. For more information, see the description of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>. 


### -param BufferSize [in]

Number of bytes to be allocated for caller-supplied data when the new element is inserted. 


### -param NewElement [out, optional]

Pointer to a variable that receives <b>TRUE</b> if a new element with the data at <i>Buffer</i> was inserted in the generic table; or <b>FALSE</b> if the new element was not inserted. 


## -returns



<b>RtlInsertElementGenericTable</b> returns a pointer to the newly inserted element's associated data, or it returns a pointer to the existing element's data if a matching element already exists in the generic table. If no matching element is found, but the new element cannot be inserted (for example, because the <i>AllocateRoutine</i> fails), <b>RtlInsertElementGenericTable</b> returns <b>NULL</b>. 




## -remarks



To insert an element, <b>RtlInsertElementGenericTable</b> calls the <i>CompareRoutine</i> and <i>AllocateRoutine</i> that were registered when the generic table was initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>. After inserting the new element, <b>RtlInsertElementGenericTable</b> rebalances the splay link tree.

When a new element is inserted into the table, its data is copied from <i>Buffer</i> into the new element. Thus the pointer returned by <b>RtlInsertElementGenericTable</b> is never equal to <i>Buffer</i>. 

If the caller's <i>CompareRoutine</i> returns <b>GenericEqual</b>, the data at <i>Buffer</i> is assumed to duplicate the data for an existing element in the generic table. In this case, <b>RtlInsertElementGenericTable</b> does not add the new element (and thus does not call the <i>AllocateRoutine</i>), because a generic table cannot have duplicate elements.

If a matching element already exists in the generic table, <b>RtlInsertElementGenericTable</b> returns a pointer to the existing element's data and sets <i>NewElement</i> to <b>FALSE</b>. 

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406468">RtlInsertElementGenericTableAvl</a> routine instead of <b>RtlInsertElementGenericTable</b>. In the call to <b>RtlInsertElementGenericTableAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlInsertElementGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

<ul>
<li>
The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

</li>
<li>
The caller-supplied <i>CompareRoutine</i> or <i>AllocateRoutine</i> contains pageable code. 

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552209">RtlDeleteElementGenericTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552989">RtlInitializeGenericTable</a>
 

 

