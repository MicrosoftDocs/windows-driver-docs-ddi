---
UID: NF:storport.StorPortInterlockedInsertTailList
title: StorPortInterlockedInsertTailList function (storport.h)
description: The StorPortInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of STOR_LIST_ENTRY structures.
old-location: storage\storportinterlockedinserttaillist.htm
tech.root: storage
ms.assetid: 56147D28-B832-4C5D-BFB7-60C4020CA299
ms.date: 03/29/2018
ms.keywords: StorPortInterlockedInsertTailList, StorPortInterlockedInsertTailList routine [Storage Devices], storage.storportinterlockedinserttaillist, storport/StorPortInterlockedInsertTailList
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortInterlockedInsertTailList
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInterlockedInsertTailList function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInterlockedInsertTailList</b> routine atomically inserts an entry at the end of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structures.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the head of the list.


### -param ListEntry [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


### -param Result

<p>Pointer to a <a href="https://msdn.microsoft.com/library/Mt790432(v=VS.85).aspx"><b>STOR_LIST_ENTRY</b></a> structure that represents the first entry of the list before the new entry was inserted.</p>


### -param Lock [in, out]

A pointer to a <b>STOR_KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>.

 You must use this spin lock only with the <b>StorPortInterlocked<i>Xxx</i>List</b> routines.


## -returns



<b>StorPortInterlockedInsertHeadList</b> returns one of the following status codes:

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547820">InsertHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt790429">StorPortInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt790430">StorPortInterlockedRemoveHeadList</a>
 

 

