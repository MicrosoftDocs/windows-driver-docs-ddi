---
UID: NF:ntifs.RtlFreeHeap
title: RtlFreeHeap function
author: windows-driver-content
description: The RtlFreeHeap routine frees a memory block that was allocated from a heap by RtlAllocateHeap.
old-location: ifsk\rtlfreeheap.htm
old-project: ifsk
ms.assetid: 5e8b6bd7-71e7-45ad-985c-fe197693ce05
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlFreeHeap, RtlFreeHeap routine [Installable File System Drivers], ntifs/RtlFreeHeap, rtlref_02e7cb93-ec45-41c9-8e58-72c221cece37.xml, ifsk.rtlfreeheap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlFreeHeap
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlFreeHeap function


## -description


The <b>RtlFreeHeap</b> routine frees a memory block that was allocated from a heap by <a href="..\ntifs\nf-ntifs-rtlallocateheap.md">RtlAllocateHeap</a>. 


## -syntax


````
BOOLEAN RtlFreeHeap(
  _In_     PVOID HeapHandle,
  _In_opt_ ULONG Flags,
  _In_     PVOID HeapBase
);
````


## -parameters




### -param HeapHandle [in]

A handle for the heap whose memory block is to be freed. This parameter is a handle returned by <a href="..\ntifs\nf-ntifs-rtlcreateheap.md">RtlCreateHeap</a>. 


### -param Flags [in, optional]

A set of flags that controls aspects of freeing a memory block. Specifying the following value overrides the corresponding value that was specified in the <i>Flags</i> parameter when the heap was created by <a href="..\ntifs\nf-ntifs-rtlcreateheap.md">RtlCreateHeap</a>. 
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

TBD



#### - HeapBase [in]

A pointer to the memory block to free. This pointer is returned by <a href="..\ntifs\nf-ntifs-rtlallocateheap.md">RtlAllocateHeap</a>. 


## -returns


<b>RtlFreeHeap</b> returns <b>TRUE</b> if the block was freed successfully;   <b> FALSE</b> otherwise.


<div class="alert"><b>Note</b>  Starting with Windows 8 the return value is typed as <b>LOGICAL</b>, which has a different size than <b>BOOLEAN</b>.</div>
<div> </div>




## -see-also

<a href="..\ntifs\nf-ntifs-rtldestroyheap.md">RtlDestroyHeap</a>

<a href="..\ntifs\nf-ntifs-rtlcreateheap.md">RtlCreateHeap</a>

<a href="..\ntifs\nf-ntifs-rtlallocateheap.md">RtlAllocateHeap</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlFreeHeap routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

