---
UID: NF:storport.StorPortInterlockedRemoveHeadList
title: StorPortInterlockedRemoveHeadList function
author: windows-driver-content
description: The StorPortInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of STOR_LIST_ENTRY structures.
old-location: storage\storportinterlockedremoveheadlist.htm
old-project: storage
ms.assetid: 6B99D78A-B582-4114-9472-D01D39FDD4C9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortInterlockedRemoveHeadList, storage.storportinterlockedremoveheadlist, StorPortInterlockedRemoveHeadList routine [Storage Devices], storport/StorPortInterlockedRemoveHeadList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	storport.h
apiname: 
-	StorPortInterlockedRemoveHeadList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInterlockedRemoveHeadList function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The StorPortInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structures. 


## -syntax


````
ULONG StorPortInterlockedRemoveHeadList(
  _In_    PVOID            HwDeviceExtension,
  _Inout_ PSTOR_LIST_ENTRY ListHead,
  _Inout_ PSTOR_LIST_ENTRY *Result,
  _Inout_ PSTOR_KSPIN_LOCK Lock
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the head of the list.


### -param Result

TBD


### -param Lock [in, out]

A pointer to a <b>STOR_KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>.

 You must use this spin lock only with the <b>StorPortInterlocked<i>Xxx</i>List</b> routines.


#### - *Result [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the entry removed from the list. If the list was empty, the routine returns <b>NULL</b>.


## -returns


<b>StorPortInterlockedRemoveHeadList</b> returns one of the following status codes:
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
The list items were removed successfully or the list is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>ListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table> 



## -see-also

<a href="..\storport\nf-storport-storportinterlockedremoveheadlist.md">StorPortInterlockedRemoveHeadList</a>

<a href="..\wdm\nf-wdm-insertheadlist.md">InsertHeadList</a>

<a href="..\storport\nf-storport-storportinterlockedinserttaillist.md">StorPortInterlockedInsertTailList</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>

<a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInterlockedRemoveHeadList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

