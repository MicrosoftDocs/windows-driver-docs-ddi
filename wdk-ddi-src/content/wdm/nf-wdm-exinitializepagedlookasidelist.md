---
UID: NF:wdm.ExInitializePagedLookasideList
title: ExInitializePagedLookasideList function (wdm.h)
description: The ExInitializePagedLookasideList routine initializes a lookaside list for pageable entries of the specified size.
tech.root: kernel
ms.date: 01/05/2023
keywords: ["ExInitializePagedLookasideList function"]
ms.keywords: ExInitializePagedLookasideList, ExInitializePagedLookasideList routine [Kernel-Mode Driver Architecture], k102_7044b56d-db76-4021-8d76-b4f157e2d783.xml, kernel.exinitializepagedlookasidelist, wdm/ExInitializePagedLookasideList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInitializePagedLookasideList
 - wdm/ExInitializePagedLookasideList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInitializePagedLookasideList
---

## -description

The **ExInitializePagedLookasideList** routine initializes a lookaside list for pageable entries of the specified size.

## -parameters

### -param Lookaside [out]

A pointer to the [PAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess) structure to initialize. The caller must use non-paged system space for the structure, even though the entries in this lookaside list will be allocated from pageable memory. On 64-bit platforms, this structure must be 16-byte aligned.

### -param Allocate [in, optional]

A pointer to either a caller-supplied function for allocating an entry when the lookaside list is empty, or to **NULL**. If non-**NULL**, the pointer is to a function with the prototype:

```cpp
PVOID XxxAllocate(
  __in POOL_TYPE  PoolType,           // PagedPool 
  __in SIZE_T  NumberOfBytes,         // value of Size
  __in ULONG  Tag                     // value of Tag
);
```

If the *Allocate* parameter is **NULL**, subsequent calls to **ExAllocateFromPagedLookasideList** automatically allocate entries whenever the lookaside list is empty.

### -param Free [in, optional]

A pointer to either a caller-supplied function for freeing an entry whenever the lookaside list is full, or to **NULL**. If non-**NULL**, the pointer is to a function with the prototype:

```cpp
VOID XxxFree(
  __in PVOID  Buffer
);
```

If the *Free* parameter is **NULL**, subsequent calls to **ExFreeToPagedLookasideList** automatically release the given entry back to paged pool whenever the list is full, that is, currently holding the system-determined maximum number of entries.

### -param Flags [in]

Starting in Windows 8, this parameter specifies an optional flag value to modify the default behavior of the **ExInitializePagedLookasideList** routine. Compatible flag bits include the following.

| Flag bit | Meaning |
|---|---|
| POOL_RAISE_IF_ALLOCATION_FAILURE | If the allocation fails, raise an exception. |

Specifying the POOL_NX_ALLOCATION flag has no effect. All pageable memory is allocated as NX.

Before Windows 8, this parameter is not used and must be zero.

### -param Size [in]

Specifies the size in bytes of each entry in the lookaside list.

### -param Tag [in]

Specifies the pool tag to use when allocating lookaside list entries. For more information about pool tags, see the *Tag* parameter of [ExAllocatePoolWithTag](./nf-wdm-exallocatepoolwithtag.md).

### -param Depth [in]

Reserved. Must be zero.

## -remarks

After calling **ExInitializePagedLookasideList**, blocks of the caller-specified *Size* can be allocated from and freed to the lookaside list with calls to [ExAllocateFromPagedLookasideList](./nf-wdm-exallocatefrompagedlookasidelist.md) and [ExFreeToPagedLookasideList](./nf-wdm-exfreetopagedlookasidelist.md), respectively. Such dynamically allocated and freed entries can be any data structure or fixed-size buffer that the caller uses while the system is running, particularly if the caller cannot predetermine how many such entries will be in use at any given moment. The layout and contents of each fixed-size entry are caller-determined.

**ExInitializePagedLookasideList** initializes the system state to track usage of the given lookaside list, as follows:

- Zero-initializes the counters to be maintained for entries.

- Stores the entry points of the caller-supplied ***Xxx*Allocate** and ***Xxx*Free** routines, if any, or sets these entry points to [ExAllocatePoolWithTag](./nf-wdm-exallocatepoolwithtag.md) and [ExFreePool](../ntddk/nf-ntddk-exfreepool.md), respectively.

- Initializes a system spin lock to control allocations from and frees to the lookaside list in a multiprocessor-safe manner if necessary.

- Stores the caller-supplied entry *Size* and list *Tag*.

- Sets up the system-determined limits (minimum  and maximum) on the number of entries to be held in the lookaside list, which can be adjusted subsequently if system-wide demand for entries is higher or lower than anticipated.

- Sets up the system-determined flags, which control the type of memory from which entries will be allocated subsequently.

The system maintains a set of all lookaside lists in use. As demand for lookaside list entries and on available paged memory varies while the system runs, the system adjusts its limits for the number of entries to be held in each paged lookaside list dynamically.

Drivers must always use explicitly free any lookaside lists they create before unloading. To do otherwise is a serious programming error. Use [ExDeletePagedLookasideList](./nf-wdm-exdeletepagedlookasidelist.md) to free the list.

**ExInitializePagedLookasideList** sets up the opaque list head at the caller-supplied location but preallocates no memory for list entries. Subsequently, the initial entries are allocated dynamically as calls to **ExAllocateFromPagedLookasideList** occur, and these initial entries are held in the lookaside list as reciprocal calls to **ExFreeToPagedLookasideList** occur. Entries collect in the given lookaside list until the system-determined maximum is reached, whereupon any additional entries are returned to paged pool as they are freed. If the list becomes empty, allocate requests are satisfied by the ***Xxx*Allocate** function specified at list initialization or by **ExAllocatePoolWithTag**.

It is more efficient to pass **NULL** pointers for the *Allocate* and *Free* parameters of **ExInitializePagedLookasideList** whenever the user of a lookaside list does nothing more than allocate and release fixed-size entries. However, any component that uses a lookaside list might supply these functions to do additional caller-determined processing, such as tracking its own dynamic memory usage by maintaining state about the number of entries it allocates and frees.

If the caller of **ExInitializePagedLookasideList** supplies an ***Xxx*Allocate** function, that function must allocate entries for the lookaside list using the given input parameters when it calls **ExAllocatePoolWithTag.**

Starting with Windows Vista, a similar routine, [ExInitializeLookasideListEx](./nf-wdm-exinitializelookasidelistex.md), initializes a lookaside list that is described by a [LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess) structure. Unlike the ***Xxx*Allocate** and ***Xxx*Free** routines for a lookaside list that uses a **PAGED_LOOKASIDE_LIST** structure, the allocation and deallocation routines for a lookaside list that uses the **LOOKASIDE_LIST_EX** structure receive a context pointer as an input parameter. These routines can use this context to store private data for the lookaside list. If your driver is intended to run only in Windows Vista and later versions of Windows, consider using **ExInitializeLookasideListEx** instead of **ExInitializePagedLookasideList**. For more information, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

## -see-also

[ExAllocateFromPagedLookasideList](./nf-wdm-exallocatefrompagedlookasidelist.md)

[ExAllocatePoolWithTag](./nf-wdm-exallocatepoolwithtag.md)

[ExDeletePagedLookasideList](./nf-wdm-exdeletepagedlookasidelist.md)

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[ExFreeToPagedLookasideList](./nf-wdm-exfreetopagedlookasidelist.md)

[ExInitializeLookasideListEx](./nf-wdm-exinitializelookasidelistex.md)

[ExInitializeNPagedLookasideList](./nf-wdm-exinitializenpagedlookasidelist.md)

[LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess)

[PAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess)