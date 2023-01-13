---
UID: NF:ntddk.RtlInitializeGenericTable
title: RtlInitializeGenericTable function (ntddk.h)
description: The RtlInitializeGenericTable routine initializes a generic table.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlInitializeGenericTable function"]
ms.keywords: RtlInitializeGenericTable, RtlInitializeGenericTable routine [Installable File System Drivers], ifsk.rtlinitializegenerictable, ntddk/RtlInitializeGenericTable, rtlref_2ef380c8-bc8a-4711-b0d1-b1c669818f2c.xml
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.irql: IRQL <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlInitializeGenericTable
 - ntddk/RtlInitializeGenericTable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlInitializeGenericTable
---

## -description

The **RtlInitializeGenericTable** routine initializes a generic table.

## -parameters

### -param Table [out]

A pointer to a caller-allocated buffer, which must be at least **sizeof**([RTL_GENERIC_TABLE](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_generic_table)) bytes in size, to contain the initialized generic table structure.

### -param CompareRoutine [in]

An entry point of a comparison callback routine, declared as follows:

```cpp
RTL_GENERIC_COMPARE_RESULTS
(*PRTL_GENERIC_COMPARE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in PVOID  FirstStruct,
    __in PVOID  SecondStruct
    ); 
```

The *CompareRoutine* parameters are as follows:

#### Table (CompareRoutine)

A pointer to the generic table.

#### FirstStruct

A pointer to the first item to be compared.

#### SecondStruct

A pointer to the second item to be compared.

The *CompareRoutine* must strictly track the ordering of all elements in the generic table so that it can identify any particular element. The caller-defined structure for element data usually includes a member whose value is unique and can be used as a sorting key. All *Rtl...GenericTable* routines that call the *CompareRoutine* take a buffer pointer as a parameter, which is passed in turn to the *CompareRoutine*. The buffer contains a caller-supplied key value to be matched by the *CompareRoutine* to the key of the element that is being searched for.

Given two such key values, the *CompareRoutine* returns **GenericLessThan**, **GenericGreaterThan**, or **GenericEqual**.

### -param AllocateRoutine [in]

An entry point of an allocation callback routine, declared as follows:

```cpp
PVOID
(*PRTL_GENERIC_ALLOCATE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in CLONG  ByteSize
    );
```

The *AllocateRoutine* parameters are as follows:

#### Table (AllocateRoutine)

A pointer to the generic table.

#### ByteSize

The number of bytes to allocate.

For each new element, the *AllocateRoutine* is called to allocate memory for caller-supplied data plus some additional memory for use by the *Rtl...GenericTable* routines. Note that because of this "additional memory," caller-supplied routines must not access the first (**sizeof**(RTL_SPLAY_LINKS) + **sizeof**(LIST_ENTRY)) bytes of any element in the generic table.

### -param FreeRoutine [in]

An entry point of a deallocation callback routine, declared as follows:

```cpp
VOID
(*PRTL_GENERIC_FREE_ROUTINE) (
    __in struct _RTL_GENERIC_TABLE  *Table,
    __in PVOID  Buffer
    );
```

The *FreeRoutine* parameters are as follows:

#### Table (FreeRoutine)

A pointer to the generic table.

#### Buffer

A pointer to the element that is being deleted.

*Rtl...GenericTable* routines call the *FreeRoutine* to deallocate memory for elements to be deleted from the generic table. The *FreeRoutine* is the opposite of the *AllocateRoutine*.

### -param TableContext [in, optional]

An optional pointer to a caller-supplied context for the generic table. This parameter can be **NULL**.

## -returns

None

## -remarks

File systems call **RtlInitializeGenericTable** to initialize a generic table to store file system-specific data, such as name-lookup information for currently open files. The sort order, structure, and contents of the elements are caller-defined.

File systems must call **RtlInitializeGenericTable** to initialize the generic table before they use any other *Rtl...GenericTable* routines on the new generic table. The initialized generic table structure should be considered opaque.

Callers of the *Rtl...GenericTable* routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

The caller-supplied *CompareRoutine* is called before the *AllocateRoutine* to locate an appropriate location at which a new element should be inserted. The *CompareRoutine* also is called before the *FreeRoutine* to locate an element to be deleted.

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including *Ntddk.h*:

```cpp
`#define RTL_USE_AVL_TABLES 0`
```

If you want to use AVL tables and if RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the [RtlInitializeGenericTableAvl](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinitializegenerictableavl) routine instead of **RtlInitializeGenericTable**. **RtlInitializeGenericTableAvl** returns an initialized [**RTL_AVL_TABLE**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_rtl_avl_table) table structure in the buffer to which the *Table* parameter points. In the call to **RtlInitializeGenericTableAvl**, the caller must pass a PRTL_AVL_COMPARE_ROUTINE-typed comparison callback routine, a PRTL_AVL_ALLOCATE_ROUTINE-typed allocation callback routine, and a PRTL_AVL_FREE_ROUTINE-typed deallocation callback routine rather than the similar PRTL_GENERIC_*Xxx*-typed routines.

Callers of **RtlInitializeGenericTable** must be running at IRQL <= DISPATCH_LEVEL. Note that if *Rtl...GenericTable* routines are to be used at IRQL DISPATCH_LEVEL, the *CompareRoutine*, *AllocateRoutine*, and *FreeRoutine* must all be nonpageable code, and the *AllocateRoutine* should allocate memory from nonpaged pool.

## -see-also

[ExInitializeFastMutex](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializefastmutex)

[RtlDeleteElementGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtldeleteelementgenerictable)

[RtlEnumerateGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictable)

[RtlEnumerateGenericTableWithoutSplaying](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlenumerategenerictablewithoutsplaying)

[RtlGetElementGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlgetelementgenerictable)

[RtlInsertElementGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlinsertelementgenerictable)

[RtlLookupElementGenericTable](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtllookupelementgenerictable)

[RtlNumberGenericTableElements](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlnumbergenerictableelements)
