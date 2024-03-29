---
UID: NF:ntifs.RtlFreeHeap
title: RtlFreeHeap function (ntifs.h)
description: The RtlFreeHeap routine frees a memory block that was allocated from a heap by RtlAllocateHeap.
old-location: ifsk\rtlfreeheap.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlFreeHeap function"]
ms.keywords: RtlFreeHeap, RtlFreeHeap routine [Installable File System Drivers], ifsk.rtlfreeheap, ntifs/RtlFreeHeap, rtlref_02e7cb93-ec45-41c9-8e58-72c221cece37.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows XP.
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFreeHeap
 - ntifs/RtlFreeHeap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFreeHeap
---

# RtlFreeHeap function


## -description

The <b>RtlFreeHeap</b> routine frees a memory block that was allocated from a heap by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a>.

## -parameters

### -param HeapHandle [in]


A handle for the heap whose memory block is to be freed. This parameter is a handle returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap">RtlCreateHeap</a>.

### -param Flags [in, optional]


A set of flags that controls aspects of freeing a memory block. Specifying the following value overrides the corresponding value that was specified in the <i>Flags</i> parameter when the heap was created by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap">RtlCreateHeap</a>. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HEAP_NO_SERIALIZE

</td>
<td>
Mutual exclusion will not be used when <b>RtlFreeHeap</b> is accessing the heap. 

</td>
</tr>
</table>

### -param BaseAddress

<p>A pointer to the memory block to free. This pointer is returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap"><b>RtlAllocateHeap</b></a>. </p>

## -returns

<b>RtlFreeHeap</b> returns <b>TRUE</b> if the block was freed successfully;   <b> FALSE</b> otherwise.


<div class="alert"><b>Note</b>  Starting with Windows 8 the return value is typed as <b>LOGICAL</b>, which has a different size than <b>BOOLEAN</b>.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreateheap">RtlCreateHeap</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldestroyheap">RtlDestroyHeap</a>
