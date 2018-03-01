---
UID: NF:storport.StorPortInterlockedPopEntrySList
title: StorPortInterlockedPopEntrySList function
author: windows-driver-content
description: Removes an item from the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system. Syntax.
old-location: storage\storportinterlockedpopentryslist.htm
old-project: storage
ms.assetid: 9DA0A057-1472-4B42-9149-A961F7D84B2E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortInterlockedPopEntrySList, StorPortInterlockedPopEntrySList routine [Storage Devices], storage.storportinterlockedpopentryslist, storport/StorPortInterlockedPopEntrySList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortInterlockedPopEntrySList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInterlockedPopEntrySList function


## -description


Removes an item from the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.
 
Syntax


## -syntax


````
ULONG StorPortInterlockedPopEntrySList(
  _In_    PVOID               HwDeviceExtension,
  _Inout_ PSTOR_SLIST_HEADER  SListHead,
  _Out_   PSTOR_SLIST_ENTRY * Result
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param SListHead [in, out]

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.


### -param Result [out]

A pointer to a list entry pointer. The value returned is a pointer to  the item removed  from the front of the list. If the list is empty, then <b>NULL</b> is returned in the value pointed to by <i>Result</i>.


## -returns



<b>StorPortInterlockedPopEntrySList</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list item was successfully removed from  the list or is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>SListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



The <b>StorPortInterlockedPopEntrySList</b> will also return <b>STATUS_SUCCESS</b> when no entries are in the list. The pointer value referenced by <i>Result</i> must be evaluated for <b>NULL</b> to verify that no entry was returned.

<b>StorPortInterlockedPopEntrySList</b> does  not free the list entry it returns. Any deallocation code for the list must take care to free memory allocated for a list entry at the location obtained prior to any adjustment for boundary alignment. The value pointed to by <i>Result</i> may not be the original buffer location allocated due to an adjustment for <b>MEMORY_ALLOCATION_ALIGNMENT</b>. See remarks for <a href="..\storport\nf-storport-storportinterlockedpushentryslist.md">StorPortInterlockedPushEntrySList</a>.




## -see-also

<a href="..\storport\nf-storport-storportinterlockedpushentryslist.md">StorPortInterlockedPushEntrySList</a>



<a href="..\storport\nf-storport-storportinterlockedflushslist.md">StorPortInterlockedFlushSList</a>



<a href="..\storport\nf-storport-storportquerydepthslist.md">StorPortQueryDepthSList</a>



<a href="..\storport\nf-storport-storportinitializeslisthead.md">StorPortInitializeSListHead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInterlockedPopEntrySList routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

