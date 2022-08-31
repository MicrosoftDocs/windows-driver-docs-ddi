---
UID: NF:wdm.ExInitializeLookasideListEx
title: ExInitializeLookasideListEx function (wdm.h)
description: The ExInitializeLookasideListEx routine initializes a lookaside list.
tech.root: kernel
ms.date: 08/29/2022
keywords: ["ExInitializeLookasideListEx function"]
ms.keywords: ExInitializeLookasideListEx, ExInitializeLookasideListEx routine [Kernel-Mode Driver Architecture], k102_1ceb4bd5-41cb-4f77-b435-a8bf922afbc2.xml, kernel.exinitializelookasidelistex, wdm/ExInitializeLookasideListEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
 - ExInitializeLookasideListEx
 - wdm/ExInitializeLookasideListEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExInitializeLookasideListEx
---

## -description

The **ExInitializeLookasideListEx** routine initializes a lookaside list.

## -parameters

### -param Lookaside [out]

A pointer to the [LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess) structure to initialize. On return, this structure describes an empty lookaside list. The caller must use nonpaged system space for this structure, regardless of whether the entries in the lookaside list are allocated from paged or nonpaged memory. On 64-bit platforms, this structure must be 16-byte aligned.

### -param Allocate [in, optional]

A pointer to a caller-supplied [LookasideListAllocateEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-allocate_function_ex) routine that allocates a new lookaside-list entry. The [ExAllocateFromLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromlookasidelistex) routine calls this *LookasideListAllocateEx* routine if the lookaside list is empty (contains no entries). This parameter is optional and can be specified as **NULL** if a custom allocation routine is not required. If this parameter is **NULL**, calls to **ExAllocateFromPagedLookasideList** automatically allocate the paged or nonpaged storage (as determined by the *PoolType* parameter) for the new entries.

### -param Free [in, optional]

A pointer to a caller-supplied [LookasideListFreeEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-free_function_ex) routine that frees a previously allocated lookaside-list entry. The [ExFreeToPagedLookasideList](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetopagedlookasidelist) routine calls this *LookasideListFreeEx* routine if the lookaside list is full (that is, the list already contains the maximum number of entries, as determined by the operating system). This parameter is optional and can be specified as **NULL** if a custom deallocation routine is not required. If this parameter is **NULL**, calls to **ExFreeToPagedLookasideList** automatically free the storage for the specified entries.

### -param PoolType [in]

Specifies the pool type of the entries in the lookaside list. Set this parameter to a valid [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type) enumeration value.

### -param Flags [in]

Specifies an optional flag value to modify the default behavior of the *LookasideListAllocateEx* routine. Set this parameter to zero or to one of the following EX_LOOKASIDE_LIST_EX_FLAGS_*XXX* flag bits.

| Flag bit | Description |
|--|--|
| EX_LOOKASIDE_LIST_EX_FLAGS_RAISE_ON_FAIL | If the allocation fails, raise an exception. |
| EX_LOOKASIDE_LIST_EX_FLAGS_FAIL_NO_RAISE | If the allocation fails, return **NULL** instead of raising an exception. This flag is intended for use with an allocation routine, such as [ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag), that charges quotas for pool usage. |

These two flag bits are mutually exclusive.

If *Allocate* is **NULL**, set *Flags* to either zero or EX_LOOKASIDE_LIST_EX_FLAGS_RAISE_ON_FAIL, but not to EX_LOOKASIDE_LIST_EX_FLAGS_FAIL_NO_RAISE. Otherwise, the behavior of the default allocation routine is undefined.

If *Flags* = EX_LOOKASIDE_LIST_EX_FLAGS_RAISE_ON_FAIL, the *PoolType* parameter value is bitwise ORed with the POOL_RAISE_IF_ALLOCATION_FAILURE flag bit to form the *PoolType* parameter value that is passed to the *LookasideListAllocateEx* routine. The *LookasideListAllocateEx* routine can pass this *PoolType* value, without modification, to the **ExAllocatePoolWithTag** routine. For more information about the POOL_RAISE_IF_ALLOCATION_FAILURE flag, see [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

If *Flags* = EX_LOOKASIDE_LIST_EX_FLAGS_FAIL_NO_RAISE, the *PoolType* parameter value is bitwise ORed with the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag bit to form the *PoolType* parameter value that is passed to the *LookasideListAllocateEx* routine. The *LookasideListAllocateEx* routine can pass this *PoolType* value, without modification, to the **ExAllocatePoolWithQuotaTag** routine. For more information about the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag, see [ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag).

### -param Size [in]

Specifies the size, in bytes, of each entry in the lookaside list.

### -param Tag [in]

Specifies the four-byte pool tag to use to mark the allocated storage for lookaside-list entries. For more information about pool tags, see the description of the *Tag* parameter in **ExAllocatePoolWithTag**.

### -param Depth [in]

Reserved. Always set this parameter to zero.

## -returns

**ExInitializeLookasideListEx** returns STATUS_SUCCESS if the call is successful. Possible return values include the following error code:

| Return code | Description |
|--|--|
| STATUS_INVALID_PARAMETER_4 | The *PoolType* parameter value is not valid. |
| STATUS_INVALID_PARAMETER_5 | The *Flags* parameter value is not valid. |

## -remarks

A driver must call this routine to initialize a lookaside list before the driver can begin to use the list. A lookaside list is a pool of fixed-size buffers that the driver can manage locally to reduce the number of calls to system allocation routines and, thereby, to improve performance. The buffers are stored as entries in the lookaside list. All entries in the list are of the same, uniform size, which is specified by the *Size* parameter.

After **ExInitializeLookasideListEx** returns, the lookaside list is initialized but contains no entries. When a client calls the [ExAllocateFromLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromlookasidelistex) routine to request an entry, this routine determines that the lookaside list is empty and calls the driver-supplied [LookasideListAllocateEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-allocate_function_ex) routine to dynamically allocate storage for a new entry. Additional entries might be allocated in response to similar requests from clients. Later, when clients call the [ExFreeToLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetolookasidelistex) to release these entries, this routine inserts the entries into the lookaside list. If the number of entries in the list reaches a limit that is determined by the operating system, **ExFreeToLookasideListEx** ceases to add further entries to the list and instead passes these entries to the driver-supplied [LookasideListFreeEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-free_function_ex) routine to be freed.

If the driver does not supply *LookasideListAllocateEx* and *LookasideListFreeEx* routines, the **ExAllocateFromLookasideListEx** and **ExFreeToLookasideListEx** routines use default allocation and deallocation routines instead.

There is no benefit to providing *LookasideListAllocateEx* and *LookasideListFreeEx* routines that do nothing but call [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag) and [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool). The same effect can be achieved with better performance by simply setting the *Allocate* and *Free* parameters to **NULL**.

Before a driver unloads, it must explicitly free any lookaside lists it created. Failure to do so is a serious programming error. Call the [ExDeleteLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletelookasidelistex) routine to free a lookaside list. This routine frees the storage for any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists.

The operating system keeps track of all lookaside lists that are currently in use. As both the amount of available nonpaged memory and the demand for lookaside list entries vary over time, the operating system dynamically adjusts its limits for the maximum number of entries in each nonpaged lookaside list.

In Windows 2000 and later versions of Windows, a lookaside list that contains paged or nonpaged entries can be described by a [PAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess) or [NPAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess) structure, respectively.

For more information about lookaside lists, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

Callers of **ExInitializeLookasideListEx** can be running at IRQL <= DISPATCH_LEVEL, but are typically running at IRQL = PASSIVE_LEVEL.

### Examples

The driver-supplied *LookasideListAllocateEx* and *LookasideListFreeEx* routines both receive *Lookaside* parameters that point to the **LOOKASIDE_LIST_EX** structure that describes the lookaside list. The routines can use this parameter to access private data that the driver has associated with the lookaside list. For example, the driver might allocate an instance of the following structure to collect private data for each lookaside list that it creates:

```cpp
typedef struct
{
  ULONG NumberOfAllocations;  // number of entries allocated
  ULONG NumberOfFrees;        // number of entries freed
  LOOKASIDE_LIST_EX LookasideField;
} MY_PRIVATE_DATA;
```

The driver can initialize a lookaside list as shown in the following code example:

```cpp
#define ENTRY_SIZE  256
#define MY_POOL_TAG  'tsLL'      
MY_PRIVATE_DATA *MyContext;
NTSTATUS status = STATUS_SUCCESS;
 
MyContext = ExAllocatePoolWithTag(NonPagedPool, sizeof(MY_PRIVATE_DATA), MY_POOL_TAG);
if (MyContext)
{
    MyContext.NumberOfAllocations = 0;
    MyContext.NumberOfFrees = 0;

    status = ExInitializeLookasideListEx(
                 &MyContext.LookasideField,
                 MyLookasideListAllocateEx,
                 MyLookasideListFreeEx,
                 NonPagedPool,
                 0,
                 ENTRY_SIZE,
                 MY_POOL_TAG,
                 0);
}
else
{
    status = STATUS_INSUFFICIENT_RESOURCES;
}
```

The following code example shows how the *LookasideListAllocateEx* routine can use its *Lookaside* parameter to access the private data that is associated with the lookaside list:

```cpp
PVOID
  MyLookasideListAllocateEx(
    __in POOL_TYPE  PoolType,
    __in SIZE_T  NumberOfBytes,
    __in ULONG  Tag,
    __inout PLOOKASIDE_LIST_EX  Lookaside)
{
    MY_PRIVATE_DATA *MyContext;
    PVOID NewEntry;

    MyContext = CONTAINING_RECORD(Lookaside, MY_PRIVATE_DATA, LookasideField);

    NewEntry = ExAllocatePoolWithTag(PoolType, NumberOfBytes, Tag);

    if (NewEntry)
    {
        MyContext->NumberOfAllocations = InterlockedIncrement(MyContext->NumberOfAllocations);
    }

    return NewEntry;
}
```

The [**CONTAINING_RECORD**](/windows/win32/api/ntdef/nf-ntdef-containing_record) macro is defined in the Ntdef.h header file. The *LookAsideListFreeEx* routine can similarly use its *Lookaside* parameter to access private data.

After the **MyLookasideListAllocateEx** routine in this example returns, **ExAllocateFromLookasideListEx** inserts the buffer pointed to by the **NewEntry** variable into the lookaside list. To make this insertion operation thread-safe, **ExAllocateFromLookasideListEx** synchronizes its access of the lookaside list with other list insertion and removal operations that might be performed by other threads. Similarly, when **ExFreeFromLookasideListEx** removes a buffer from the lookaside list, it synchronizes its access to the list.

**ExAllocateFromLookasideListEx** and **ExFreeFromLookasideListEx** do not synchronize their calls to driver-supplied [LookasideListAllocateEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-allocate_function_ex) and [LookasideListFreeEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-free_function_ex) routines. Thus, if the **MyLookasideListAllocateEx** and **MyLookasideListFreeEx** routines in the preceding code examples must be thread-safe, the driver must provide the necessary synchronization.

The example routine, **MyLookasideListAllocateEx**, synchronizes its access of the **MyContext->NumberOfAllocations** variable with other threads that might increment and decrement this variable. To provide this synchronization, **MyLookasideListAllocateEx** calls the [InterlockedIncrement](/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement) routine to atomically increment this variable. Similarly, the **MyLookasideListFreeEx** routine (not shown) can call the [InterlockedDecrement](/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement) routine to atomically decrement this variable.

However, if the sole purpose of the **MyContext->NumberOfAllocations** variable in the preceding code example is simply to gather statistics on lookaside list allocations, atomic increments and decrements are hardly necessary. In this case, the remote possibility of a missed increment or decrement should not be a concern.

For more information about thread safety for lookaside lists, see [Using Lookaside Lists](/windows-hardware/drivers/kernel/using-lookaside-lists).

## -see-also

[ExAllocateFromLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromlookasidelistex)

[ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag)

[ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag)

[ExDeleteLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletelookasidelistex)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[ExFreeToLookasideListEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetolookasidelistex)

[InterlockedDecrement](/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockeddecrement)

[InterlockedIncrement](/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedincrement)

[LOOKASIDE_LIST_EX](/windows-hardware/drivers/kernel/eprocess)

[LookasideListAllocateEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-allocate_function_ex)

[LookasideListFreeEx](/windows-hardware/drivers/ddi/wdm/nc-wdm-free_function_ex)

[NPAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess)

[PAGED_LOOKASIDE_LIST](/windows-hardware/drivers/kernel/eprocess)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
