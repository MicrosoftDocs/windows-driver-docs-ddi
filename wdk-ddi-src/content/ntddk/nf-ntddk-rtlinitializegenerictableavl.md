---
UID: NF:ntddk.RtlInitializeGenericTableAvl
title: RtlInitializeGenericTableAvl function (ntddk.h)
description: The RtlInitializeGenericTableAvl routine initializes a generic table using Adelson-Velsky/Landis (AVL) trees.
old-location: ifsk\rtlinitializegenerictableavl.htm
tech.root: ifsk
ms.assetid: D89713A8-7CE7-4A87-AED7-62ACF7D1BA06
ms.date: 04/16/2018
keywords: ["RtlInitializeGenericTableAvl function"]
ms.keywords: RtlInitializeGenericTableAvl, RtlInitializeGenericTableAvl routine [Installable File System Drivers], ifsk.rtlinitializegenerictableavl, ntddk/RtlInitializeGenericTableAvl
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlInitializeGenericTableAvl
 - ntddk/RtlInitializeGenericTableAvl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlInitializeGenericTableAvl
---

# RtlInitializeGenericTableAvl function


## -description

The <b>RtlInitializeGenericTableAvl</b> routine initializes a generic table using Adelson-Velsky/Landis (AVL) trees.

## -parameters

### -param Table 

[out]
A pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table">RTL_AVL_TABLE</a>) bytes in size, to contain the initialized generic table structure.

### -param CompareRoutine 

[in]
An entry point of a comparison callback routine, declared as follows:


```
RTL_GENERIC_COMPARE_RESULTS
(*PRTL_AVL_COMPARE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in PVOID  FirstStruct,
    __in PVOID  SecondStruct
    ); 
```

The <i>CompareRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### FirstStruct

A pointer to the first item to be compared.



#### SecondStruct

A pointer to the second item to be compared.

The <i>CompareRoutine</i> must strictly track the ordering of all elements in the generic table so that it can identify any particular element. The caller-defined structure for element data usually includes a member whose value is unique and can be used as a sorting key. All <i>Rtl...GenericTableAvl</i> routines that call the <i>CompareRoutine</i> take a buffer pointer as a parameter, which is passed in turn to the <i>CompareRoutine</i>. The buffer contains a caller-supplied key value to be matched by the <i>CompareRoutine</i> to the key of the element that is being searched for. 

Given two such key values, the <i>CompareRoutine</i> returns <b>GenericLessThan</b>, <b>GenericGreaterThan</b>, or <b>GenericEqual</b>.

### -param AllocateRoutine 

[in]
An entry point of an allocation callback routine, declared as follows:


```
PVOID
(*PRTL_AVL_ALLOCATE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in CLONG  ByteSize
    );
```

The <i>AllocateRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### ByteSize

The number of bytes to allocate.

For each new element, the <i>AllocateRoutine</i> is called to allocate memory for caller-supplied data plus some additional memory for use by the <i>Rtl...GenericTableAvl</i> routines. Note that because of this "additional memory," caller-supplied routines must not access the first <b>sizeof</b>(RTL_BALANCED_LINKS) bytes of any element in the generic table.

### -param FreeRoutine 

[in]
An entry point of a deallocation callback routine, declared as follows:


```
VOID
(*PRTL_AVL_FREE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in PVOID  Buffer
    );
```

The <i>FreeRoutine</i> parameters are as follows:





#### Table

A pointer to the generic table.



#### Buffer

A pointer to the element that is being deleted.

<i>Rtl...GenericTableAvl</i> routines call the <i>FreeRoutine</i> to deallocate memory for elements to be deleted from the generic table. The <i>FreeRoutine</i> is the opposite of the <i>AllocateRoutine</i>.

### -param TableContext 

[in, optional]
An optional pointer to a caller-supplied context for the generic table. This parameter can be <b>NULL</b>.

## -returns

None

## -remarks

File systems call <b>RtlInitializeGenericTableAvl</b> to initialize a generic table to store file system-specific data, such as name-lookup information for currently open files. The sort order, structure, and contents of the elements are caller-defined. 

File systems must call <b>RtlInitializeGenericTableAvl</b> to initialize the generic table before they use any other <i>Rtl...GenericTableAvl</i> routines on the new generic table. The initialized generic table structure should be considered opaque.

Callers of the <i>Rtl...GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

The caller-supplied <i>CompareRoutine</i> is called before the <i>AllocateRoutine</i> to locate an appropriate location at which a new element should be inserted. The <i>CompareRoutine</i> also is called before the <i>FreeRoutine</i> to locate an element to be deleted.

The <b>RtlInitializeGenericTableAvl</b> routine explicitlly allocates a generic table that uses AVL trees. Use of this routine and the other <i>Rtl...GenericTableAvl</i> routines is necessary when AVL tree based tables are desired and RTL_USE_AVL_TABLES is not define before including <i>Ntddk.h</i>.

 If you want to configure the generic table routines, <i>Rtl...GenericTable</i>, to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:


```
#define RTL_USE_AVL_TABLES 0
```

Callers of <b>RtlInitializeGenericTableAvl</b> must be running at IRQL <= DISPATCH_LEVEL. Note that if <i>Rtl...GenericTableAvl</i> routines are to be used at IRQL DISPATCH_LEVEL, the <i>CompareRoutine</i>, <i>AllocateRoutine</i>, and <i>FreeRoutine</i> must all be nonpageable code, and the <i>AllocateRoutine</i> should allocate memory from nonpaged pool.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex">ExInitializeFastMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictableavl">RtlDeleteElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictableavl">RtlEnumerateGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictableavl">RtlGetElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictable">RtlInitializeGenericTable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictableavl">RtlInsertElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictableavl">RtlLookupElementGenericTableAvl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelementsavl">RtlNumberGenericTableElementsAvl</a>

