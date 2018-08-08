---
UID: NF:storport.StorPortInterlockedPushEntrySList
title: StorPortInterlockedPushEntrySList function
author: windows-driver-content
description: Inserts an item at the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.
old-location: storage\storportinterlockedpushentryslist.htm
tech.root: storage
ms.assetid: 74C32E55-79C6-449A-AFA3-27858CF4EA6B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortInterlockedPushEntrySList, StorPortInterlockedPushEntrySList routine [Storage Devices], storage.storportinterlockedpushentryslist, storport/StorPortInterlockedPushEntrySList
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
req.lib: 
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
-	StorPortInterlockedPushEntrySList
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInterlockedPushEntrySList function


## -description


Inserts  an item at the front of a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param SListHead [in, out]

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.


### -param SListEntry [in, out]

A pointer to an <b>STOR_SLIST_ENTRY</b> structure that represents the item to insert into the singly linked list.


### -param Result [out]

A pointer to a list entry pointer. The value returned is a pointer to  the previous item that existed  at the front of the list. This pervious item remains in the list behind the item new item added from <i>SListEntry</i>. If the list is empty, then <b>NULL</b> is returned in value pointed to by <i>Result</i>.


## -returns



<b>StorPortInterlockedPushEntrySList</b> returns one of the following status codes:

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
The list item was successfully inserted into the list or is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>SListHead</i>, <i>SListEntry</i>, or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



When allocated by the caller,  the <b>STOR_SLIST_ENTRY</b> structure pointed to by <i>SListEntry</i> must be aligned at  a <b>MEMORY_ALLOCATION_ALIGNMENT</b> boundary. <b>MEMORY_ALLOCATION_ALIGNMENT</b> is defined in <i>miniport.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967735">StorPortInitializeSListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967736">StorPortInterlockedFlushSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967737">StorPortInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967739">StorPortQueryDepthSList</a>
 

 

