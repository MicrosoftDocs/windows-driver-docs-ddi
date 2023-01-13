---
UID: NF:wdm.ExInitializeNPagedLookasideList
title: ExInitializeNPagedLookasideList function (wdm.h)
description: The ExInitializeNPagedLookasideList routine initializes a lookaside list for nonpaged entries of the specified size.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["ExInitializeNPagedLookasideList function"]
ms.keywords: ExInitializeNPagedLookasideList, ExInitializeNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_054ed856-4da7-42e9-a413-baefdd1064ed.xml, kernel.exinitializenpagedlookasidelist, wdm/ExInitializeNPagedLookasideList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - ExInitializeNPagedLookasideList
 - wdm/ExInitializeNPagedLookasideList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInitializeNPagedLookasideList
---

## -description

The **ExInitializeNPagedLookasideList** routine initializes a lookaside list for nonpaged entries of the specified size.

## -parameters

### -param Lookaside [out]

A pointer to the [NPAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess) structure to initialize. The caller must use nonpaged system space for the structure. On 64-bit platforms, this structure must be 16-byte aligned.

### -param Allocate [in, optional]

A pointer to either a caller-supplied function for allocating an entry when the lookaside list is empty, or to **NULL**. If non-**NULL**, the pointer is to a function with the prototype:

```cpp
PVOID XxxAllocate(
  __in POOL_TYPE  PoolType,           // NonPagedPool 
  __in SIZE_T  NumberOfBytes,         // value of Size
  __in ULONG  Tag                     // value of Tag
);
```

If the *Allocate* parameter is **NULL**, subsequent calls to [ExAllocateFromNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist) automatically allocate entries whenever the lookaside list is empty.

### -param Free [in, optional]

A pointer to either a caller-supplied function for freeing an entry whenever the lookaside list is full, or to **NULL**. If non-**NULL**, the pointer is to a function with the prototype:

```cpp
VOID XxxFree(
  __in PVOID  Buffer
);
```

If the *Free* parameter is **NULL**, subsequent calls to [ExFreeToNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist) automatically release the given entry back to nonpaged pool whenever the list is full, that is, currently holding the system-determined maximum number of entries.

### -param Flags [in]

Starting in Windows 8, this parameter specifies an optional flag value to modify the default behavior of the **ExInitializeNPagedLookasideList** routine. Compatible flag bits include the following.

| Flag bit | Meaning | Value |
|---|---|---|
| POOL_RAISE_IF_ALLOCATION_FAILURE | If the allocation fails, raise an exception. | 16 |
| POOL_NX_ALLOCATION | Allocate non-executable memory. | 512 |

Before Windows 8, this parameter is not used and must be zero.

### -param Size [in]

Specifies the size, in bytes, for each nonpaged entry to be allocated subsequently. This parameter must not be less than the required minimum size, LOOKASIDE_MINIMUM_BLOCK_SIZE, which is defined in the Wdm.h header file.

### -param Tag [in]

Specifies the pool tag to use when allocating lookaside list entries. For more information about pool tags, see the *Tag* parameter of [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

### -param Depth [in]

Reserved. Must be zero.

## -remarks

After calling **ExInitializeNPagedLookasideList**, memory blocks of the caller-specified *Size* can be allocated from and freed to the lookaside list with calls to [ExAllocateFromNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist) and [ExFreeToNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist), respectively. Such dynamically allocated and freed entries can be any data structure or fixed-size buffer that the caller uses while the system is running, particularly if the caller cannot predetermine how many such entries will be in use at any given moment. The layout and contents of each fixed-size entry are caller-determined.

**ExInitializeNPagedLookasideList** initializes the system state to track usage of the given lookaside list, as follows:

- Zero-initializes the counters to be maintained for entries.

- Stores the entry points of the caller-supplied ***Xxx*Allocate** and ***Xxx*Free** routines, if any, or sets these entry points to [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag) and [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool), respectively.

- Initializes a system spin lock to control allocations from and frees to the lookaside list in a multiprocessor-safe manner if necessary.

- Stores the caller-supplied entry *Size* and list *Tag*.

- Sets up the system-determined limits (minimum and maximum) on the number of entries to be held in the lookaside list, which can be adjusted subsequently if system-wide demand for entries is higher or lower than anticipated.

- Sets up the system-determined flags, which control the type of memory from which entries will be allocated subsequently.

The system maintains a set of all lookaside lists currently in use. As demand for lookaside list entries and on available nonpaged memory varies while the system runs, the system adjusts its limits for the number of entries to be held in each nonpaged lookaside list dynamically.

Drivers must always explicitly free any lookaside lists they create before unloading. To do otherwise is a serious programming error. Use [ExDeleteNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletenpagedlookasidelist) to free the list.

**ExInitializeNPagedLookasideList** sets up the opaque list head at the caller-supplied location but preallocates no memory for list entries. Subsequently, the initial entries are allocated dynamically as calls to **ExAllocateFromNPagedLookasideList** occur, and these initial entries are held in the lookaside list as reciprocal calls to **ExFreeToNPagedLookasideList** occur. Entries collect in the given lookaside list until the system-determined maximum is reached, whereupon any additional entries are returned to nonpaged pool as they are freed. If the list becomes empty, allocate requests are satisfied by the ***Xxx*Allocate** function specified at list initialization or by [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

It is more efficient to pass **NULL** pointers for the *Allocate* and *Free* parameters of **ExInitializeNPagedLookasideList** whenever the user of a lookaside list does nothing more than allocate and release fixed-size entries. However, any component that uses a lookaside list might supply these functions to do additional caller-determined processing, such as tracking its own dynamic memory usage by maintaining state about the number of entries it allocates and frees.

If the caller of **ExInitializeNPagedLookasideList** supplies an ***Xxx*Allocate** function, that routine must allocate entries for the lookaside list using the given input parameters when it calls **ExAllocatePoolWithTag.**

Starting with Windows Vista, a similar routine, [ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex), initializes a lookaside list that is described by a [LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess) structure. Unlike the ***Xxx*Allocate** and ***Xxx*Free** routines for a lookaside list that uses an **NPAGED_LOOKASIDE_LIST** structure, the allocation and deallocation routines for a lookaside list that uses the **LOOKASIDE_LIST_EX** structure receive a context pointer as an input parameter. These routines can use this context to store private data for the lookaside list. If your driver is intended to run only in Windows Vista and later versions of Windows, consider using **ExInitializeLookasideListEx** instead of **ExInitializeNPagedLookasideList**. For more information, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

Callers of **ExInitializeNPagedLookasideList** can be running at IRQL <= DISPATCH_LEVEL, but are typically running at IRQL = PASSIVE_LEVEL.

## -see-also

[ExAllocateFromNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist)

[ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag)

[ExDeleteNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletenpagedlookasidelist)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[ExFreeToNPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist)

[ExInitializeLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex)

[ExInitializePagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist)

[LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess)

[NPAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess)
