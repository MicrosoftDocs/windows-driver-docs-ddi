---
UID: NF:ntddk.RtlInitializeGenericTable
title: RtlInitializeGenericTable function (ntddk.h)
description: The RtlInitializeGenericTable routine initializes a generic table.
old-location: ifsk\rtlinitializegenerictable.htm
tech.root: ifsk
ms.assetid: 99a91bb4-4fcd-4b49-bd1e-4551027b5d1f
ms.date: 04/16/2018
ms.keywords: RtlInitializeGenericTable, RtlInitializeGenericTable routine [Installable File System Drivers], ifsk.rtlinitializegenerictable, ntddk/RtlInitializeGenericTable, rtlref_2ef380c8-bc8a-4711-b0d1-b1c669818f2c.xml
f1_keywords:
 - "ntddk/RtlInitializeGenericTable"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of all Windows operating systems.
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlInitializeGenericTable
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlInitializeGenericTable function


## -description


The <b>RtlInitializeGenericTable</b> routine initializes a generic table. 


## -parameters




### -param Table [out]

A pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table">RTL_GENERIC_TABLE</a>) bytes in size, to contain the initialized generic table structure. 


### -param CompareRoutine [in]

An entry point of a comparison callback routine, declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RTL_GENERIC_COMPARE_RESULTS
(*PRTL_GENERIC_COMPARE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in PVOID  FirstStruct,
    __in PVOID  SecondStruct
    ); </pre>
</td>
</tr>
</table></span></div>
The <i>CompareRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### FirstStruct

A pointer to the first item to be compared.



#### SecondStruct

A pointer to the second item to be compared.

The <i>CompareRoutine</i> must strictly track the ordering of all elements in the generic table so that it can identify any particular element. The caller-defined structure for element data usually includes a member whose value is unique and can be used as a sorting key. All <i>Rtl...GenericTable</i> routines that call the <i>CompareRoutine</i> take a buffer pointer as a parameter, which is passed in turn to the <i>CompareRoutine</i>. The buffer contains a caller-supplied key value to be matched by the <i>CompareRoutine</i> to the key of the element that is being searched for. 

Given two such key values, the <i>CompareRoutine</i> returns <b>GenericLessThan</b>, <b>GenericGreaterThan</b>, or <b>GenericEqual</b>. 


### -param AllocateRoutine [in]

An entry point of an allocation callback routine, declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID
(*PRTL_GENERIC_ALLOCATE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in CLONG  ByteSize
    );</pre>
</td>
</tr>
</table></span></div>
The <i>AllocateRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### ByteSize

The number of bytes to allocate.

For each new element, the <i>AllocateRoutine</i> is called to allocate memory for caller-supplied data plus some additional memory for use by the <i>Rtl...GenericTable</i> routines. Note that because of this "additional memory," caller-supplied routines must not access the first (<b>sizeof</b>(RTL_SPLAY_LINKS) + <b>sizeof</b>(LIST_ENTRY)) bytes of any element in the generic table. 


### -param FreeRoutine [in]

An entry point of a deallocation callback routine, declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PRTL_GENERIC_FREE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in PVOID  Buffer
    );</pre>
</td>
</tr>
</table></span></div>
The <i>FreeRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### Buffer

A pointer to the element that is being deleted.

<i>Rtl...GenericTable</i> routines call the <i>FreeRoutine</i> to deallocate memory for elements to be deleted from the generic table. The <i>FreeRoutine</i> is the opposite of the <i>AllocateRoutine</i>. 


### -param TableContext [in, optional]

An optional pointer to a caller-supplied context for the generic table. This parameter can be <b>NULL</b>.


## -returns



None




## -remarks



File systems call <b>RtlInitializeGenericTable</b> to initialize a generic table to store file system-specific data, such as name-lookup information for currently open files. The sort order, structure, and contents of the elements are caller-defined. 

File systems must call <b>RtlInitializeGenericTable</b> to initialize the generic table before they use any other <i>Rtl...GenericTable</i> routines on the new generic table. The initialized generic table structure should be considered opaque.

Callers of the <i>Rtl...GenericTable</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

The caller-supplied <i>CompareRoutine</i> is called before the <i>AllocateRoutine</i> to locate an appropriate location at which a new element should be inserted. The <i>CompareRoutine</i> also is called before the <i>FreeRoutine</i> to locate an element to be deleted.

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define RTL_USE_AVL_TABLES 0</pre>
</td>
</tr>
</table></span></div>
If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl">RtlInitializeGenericTableAvl</a> routine instead of <b>RtlInitializeGenericTable</b>. <b>RtlInitializeGenericTableAvl</b> returns an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a> table structure in the buffer to which the <i>Table</i> parameter points. In the call to <b>RtlInitializeGenericTableAvl</b>, the caller must pass a PRTL_AVL_COMPARE_ROUTINE-typed comparison callback routine, a PRTL_AVL_ALLOCATE_ROUTINE-typed allocation callback routine, and a PRTL_AVL_FREE_ROUTINE-typed deallocation callback routine rather than the similar PRTL_GENERIC_<i>Xxx</i>-typed routines.

Callers of <b>RtlInitializeGenericTable</b> must be running at IRQL <= DISPATCH_LEVEL. Note that if <i>Rtl...GenericTable</i> routines are to be used at IRQL DISPATCH_LEVEL, the <i>CompareRoutine</i>, <i>AllocateRoutine</i>, and <i>FreeRoutine</i> must all be nonpageable code, and the <i>AllocateRoutine</i> should allocate memory from nonpaged pool.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable">RtlDeleteElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictable">RtlEnumerateGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictable">RtlGetElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable">RtlInsertElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable">RtlLookupElementGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>
 

 

