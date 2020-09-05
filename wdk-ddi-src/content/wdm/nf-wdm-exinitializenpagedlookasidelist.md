---
UID: NF:wdm.ExInitializeNPagedLookasideList
title: ExInitializeNPagedLookasideList function (wdm.h)
description: The ExInitializeNPagedLookasideList routine initializes a lookaside list for nonpaged entries of the specified size.
old-location: kernel\exinitializenpagedlookasidelist.htm
tech.root: kernel
ms.assetid: d783feff-d187-4a2f-8d3d-b5221b03459a
ms.date: 04/30/2018
keywords: ["ExInitializeNPagedLookasideList function"]
ms.keywords: ExInitializeNPagedLookasideList, ExInitializeNPagedLookasideList routine [Kernel-Mode Driver Architecture], k102_054ed856-4da7-42e9-a413-baefdd1064ed.xml, kernel.exinitializenpagedlookasidelist, wdm/ExInitializeNPagedLookasideList
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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

# ExInitializeNPagedLookasideList function


## -description

The <b>ExInitializeNPagedLookasideList</b> routine initializes a lookaside list for nonpaged entries of the specified size.

## -parameters

### -param Lookaside 

[out]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a> structure to initialize. The caller must use nonpaged system space for the structure. On 64-bit platforms, this structure must be 16-byte aligned.

### -param Allocate 

[in, optional]
A pointer to either a caller-supplied function for allocating an entry when the lookaside list is empty, or to <b>NULL</b>. If non-<b>NULL</b>, the pointer is to a function with the prototype:


```
PVOID XxxAllocate(
  __in POOL_TYPE  PoolType,           // NonPagedPool 
  __in SIZE_T  NumberOfBytes,         // value of Size
  __in ULONG  Tag                     // value of Tag
);
```

If the <i>Allocate</i> parameter is <b>NULL</b>, subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> automatically allocate entries whenever the lookaside list is empty.

### -param Free 

[in, optional]
A pointer to either a caller-supplied function for freeing an entry whenever the lookaside list is full, or to <b>NULL</b>. If non-<b>NULL</b>, the pointer is to a function with the prototype:


```
VOID XxxFree(
  __in PVOID  Buffer
);
```

If the <i>Free</i> parameter is <b>NULL</b>, subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist">ExFreeToNPagedLookasideList</a> automatically release the given entry back to nonpaged pool whenever the list is full, that is, currently holding the system-determined maximum number of entries.

### -param Flags 

[in]
Starting in Windows 8, this parameter specifies an optional flag value to modify the default behavior of the <b>ExInitializeNPagedLookasideList</b> routine. Compatible flag bits include the following.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
POOL_NX_ALLOCATION

</td>
<td>
Allocate non-executable memory.

</td>
</tr>
<tr>
<td>
POOL_RAISE_IF_ALLOCATION_FAILURE

</td>
<td>
If the allocation fails, raise an exception.

</td>
</tr>
</table>
 

Before Windows 8, this parameter is not used and must be zero.

### -param Size 

[in]
Specifies the size, in bytes, for each nonpaged entry to be allocated subsequently. This parameter must not be less than the required minimum size, LOOKASIDE_MINIMUM_BLOCK_SIZE, which is defined in the Wdm.h header file.

### -param Tag 

[in]
Specifies the pool tag to use when allocating lookaside list entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.

### -param Depth 

[in]
Reserved. Must be zero.

## -remarks

After calling <b>ExInitializeNPagedLookasideList</b>, memory blocks of the caller-specified <i>Size</i> can be allocated from and freed to the lookaside list with calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist">ExFreeToNPagedLookasideList</a>, respectively. Such dynamically allocated and freed entries can be any data structure or fixed-size buffer that the caller uses while the system is running, particularly if the caller cannot predetermine how many such entries will be in use at any given moment. The layout and contents of each fixed-size entry are caller-determined. 

<b>ExInitializeNPagedLookasideList</b> initializes the system state to track usage of the given lookaside list, as follows:

<ul>
<li>
Zero-initializes the counters to be maintained for entries.

</li>
<li>
Stores the entry points of the caller-supplied <b><i>Xxx</i>Allocate</b> and <b><i>Xxx</i>Free</b> routines, if any, or sets these entry points to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>, respectively.

</li>
<li>
Initializes a system spin lock to control allocations from and frees to the lookaside list in a multiprocessor-safe manner if necessary.

</li>
<li>
Stores the caller-supplied entry <i>Size</i> and list <i>Tag</i>.

</li>
<li>
Sets up the system-determined limits (minimum and maximum) on the number of entries to be held in the lookaside list, which can be adjusted subsequently if system-wide demand for entries is higher or lower than anticipated.

</li>
<li>
Sets up the system-determined flags, which control the type of memory from which entries will be allocated subsequently.

</li>
</ul>
The system maintains a set of all lookaside lists currently in use. As demand for lookaside list entries and on available nonpaged memory varies while the system runs, the system adjusts its limits for the number of entries to be held in each nonpaged lookaside list dynamically.

Drivers must always explicitly free any lookaside lists they create before unloading. To do otherwise is a serious programming error. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletenpagedlookasidelist">ExDeleteNPagedLookasideList</a> to free the list.

<b>ExInitializeNPagedLookasideList</b> sets up the opaque list head at the caller-supplied location but preallocates no memory for list entries. Subsequently, the initial entries are allocated dynamically as calls to <b>ExAllocateFromNPagedLookasideList</b> occur, and these initial entries are held in the lookaside list as reciprocal calls to <b>ExFreeToNPagedLookasideList</b> occur. Entries collect in the given lookaside list until the system-determined maximum is reached, whereupon any additional entries are returned to nonpaged pool as they are freed. If the list becomes empty, allocate requests are satisfied by the <b><i>Xxx</i>Allocate</b> function specified at list initialization or by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.

It is more efficient to pass <b>NULL</b> pointers for the <i>Allocate</i> and <i>Free</i> parameters of <b>ExInitializeNPagedLookasideList</b> whenever the user of a lookaside list does nothing more than allocate and release fixed-size entries. However, any component that uses a lookaside list might supply these functions to do additional caller-determined processing, such as tracking its own dynamic memory usage by maintaining state about the number of entries it allocates and frees.

If the caller of <b>ExInitializeNPagedLookasideList</b> supplies an <b><i>Xxx</i>Allocate</b> function, that routine must allocate entries for the lookaside list using the given input parameters when it calls <b>ExAllocatePoolWithTag.</b>

Starting with Windows Vista, a similar routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>, initializes a lookaside list that is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a> structure. Unlike the <b><i>Xxx</i>Allocate</b> and <b><i>Xxx</i>Free</b> routines for a lookaside list that uses an <b>NPAGED_LOOKASIDE_LIST</b> structure, the allocation and deallocation routines for a lookaside list that uses the <b>LOOKASIDE_LIST_EX</b> structure receive a context pointer as an input parameter. These routines can use this context to store private data for the lookaside list. If your driver is intended to run only in Windows Vista and later versions of Windows, consider using <b>ExInitializeLookasideListEx</b> instead of <b>ExInitializeNPagedLookasideList</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-lookaside-lists">Using Lookaside Lists</a>.

Callers of <b>ExInitializeNPagedLookasideList</b> can be running at IRQL <= DISPATCH_LEVEL, but are typically running at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletenpagedlookasidelist">ExDeleteNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreetonpagedlookasidelist">ExFreeToNPagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializelookasidelistex">ExInitializeLookasideListEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializepagedlookasidelist">ExInitializePagedLookasideList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">LOOKASIDE_LIST_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">NPAGED_LOOKASIDE_LIST</a>

