---
UID: NC:wdm.ALLOCATE_FUNCTION_EX
title: ALLOCATE_FUNCTION_EX (wdm.h)
description: The LookasideListAllocateEx routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["ALLOCATE_FUNCTION_EX callback function"]
ms.keywords: ALLOCATE_FUNCTION_EX, DrvrRtns_a8e59075-4ed4-49d3-a516-6cee5b6390c8.xml, LookasideListAllocateEx, LookasideListAllocateEx routine [Kernel-Mode Driver Architecture], kernel.lookasidelistallocateex, wdm/LookasideListAllocateEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - ALLOCATE_FUNCTION_EX
 - wdm/ALLOCATE_FUNCTION_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ALLOCATE_FUNCTION_EX
---

## -description

The *LookasideListAllocateEx* routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty.

## -parameters

### -param PoolType [in]

Specifies the type of storage to allocate for the new lookaside-list entry. The caller sets this parameter to a valid [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type) enumeration value, and possibly bitwise ORs this value with one of the following flag bits:

- POOL_RAISE_IF_ALLOCATION_FAILURE

- POOL_QUOTA_FAIL_INSTEAD_OF_RAISE

For more information about the POOL_RAISE_IF_ALLOCATION_FAILURE flag, see [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag). For more information about the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag, see [ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag).

If, in the [ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex) call that initialized the lookaside list, the *Flags* parameter is zero, the *PoolType* parameter that the *LookasideListAllocateEx* routine receives is the same *PoolType* parameter value that was passed to **ExInitializeLookasideListEx**.

If, in the **ExInitializeLookasideListEx** call, *Flags* = EX_LOOKASIDE_LIST_EX_FLAGS_RAISE_ON_FAIL, the *PoolType* parameter that the *LookasideListAllocateEx* routine receives is the bitwise OR of POOL_RAISE_IF_ALLOCATION_FAILURE and the *PoolType* parameter value that was passed to **ExInitializeLookasideListEx**. The *LookasideListAllocateEx* routine can pass its *PoolType* parameter value, without modification, to the **ExAllocatePoolWithTag** routine.

If, in the **ExInitializeLookasideListEx** call, Flags = EX_LOOKASIDE_LIST_EX_FLAGS_FAIL_NO_RAISE, the *PoolType* parameter that the *LookasideListAllocateEx* routine receives is the bitwise OR of POOL_QUOTA_FAIL_INSTEAD_OF_RAISE and the *PoolType* value that was passed to **ExInitializeLookasideListEx**.  The *LookasideListAllocateEx* routine can pass its *PoolType* parameter value, without modification, to the **ExAllocatePoolWithQuotaTag** routine.

### -param NumberOfBytes [in]

Specifies the size, in bytes, of the lookaside-list entry to allocate.

### -param Tag [in]

Specifies the four-byte pool tag to use to mark the allocated storage for the new lookaside-list entry. For more information about pool tags, see the description of the *Tag* parameter in [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

### -param Lookaside [in, out]

A pointer to a [LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess) structure that describes the lookaside list. This structure was previously initialized by the [ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex) routine.

## -returns

*LookasideListAllocateEx* returns a pointer to the allocated lookaside-list entry. If the routine cannot allocate an entry, it returns **NULL**.

## -remarks

A driver that creates a lookaside list can implement a *LookasideListAllocateEx* routine to dynamically allocate buffers for the list. A buffer that is not in use is stored as an entry in the list. All entries in a lookaside list are buffers of a uniform size, which the driver specifies when the list is initialized.

The driver supplies a pointer to a custom *LookasideListAllocateEx* routine as an input parameter in the **ExInitializeLookasideListEx** call that initializes the lookaside list. If the driver sets this parameter to **NULL**, the lookaside list uses a default allocation routine instead.

A driver calls the [ExAllocateFromLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromlookasidelistex) routine to allocate an entry from a lookaside list. If the list is empty (contains no entries), **ExAllocateFromLookasideListEx** calls *LookasideListAllocateEx* to dynamically allocate the storage for a new entry. *LookasideListAllocateEx* returns a pointer to the newly allocated entry if the allocation is successful. Otherwise, it returns **NULL**.

The *PoolType*, *NumberOfBytes*, *Tag*, and *Lookaside* parameters contain the same values that were passed as input parameters in the **ExInitializeLookasideListEx** call that initialized the lookaside list.

The *LookasideListAllocateEx* routine can use the *Lookaside* parameter to access private context data that the driver has associated with the lookaside list. For more information, see the code example in [ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex).

For more information about lookaside lists, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

The *LookasideListAllocateEx* routine is called at the same IRQL as the call to **ExAllocateFromLookasideListEx** that requests the entry. For a call that requests an entry that resides in paged memory, the caller must be running IRQL <= APC_LEVEL. For a call that requests an entry that resides in nonpaged memory, the caller must be running IRQL <= DISPATCH_LEVEL.

### Examples

To define a *LookasideListAllocateEx* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *LookasideListAllocateEx* callback routine that is named `MyLookasideListAllocateEx`, use the FREE_FUNCTION_EX type as shown in this code example:

```cpp
FREE_FUNCTION_EX MyLookasideListFreeEx;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyLookasideListFreeEx(
    PVOID  Buffer,
    PLOOKASIDE_LIST_EX  Lookaside
    )
  {
      // Function body
  }
```

The FREE_FUNCTION_EX function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the FREE_FUNCTION_EX function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[ExAllocateFromLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromlookasidelistex)

[ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag)

[ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag)

[ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex)

[LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
