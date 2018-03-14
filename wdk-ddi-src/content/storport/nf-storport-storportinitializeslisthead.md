---
UID: NF:storport.StorPortInitializeSListHead
title: StorPortInitializeSListHead function
author: windows-driver-content
description: Initializes the head of a Storport managed singly linked list.
old-location: storage\storportinitializeslisthead.htm
old-project: storage
ms.assetid: E8EF5995-67AE-4F34-B885-CBADDF3D151F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortInitializeSListHead, StorPortInitializeSListHead routine [Storage Devices], storage.storportinitializeslisthead, storport/StorPortInitializeSListHead
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
-	StorPortInitializeSListHead
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInitializeSListHead function


## -description


Initializes the head of a Storport managed singly linked list.


## -syntax


````
ULONG StorPortInitializeSListHead(
  _In_    PVOID              HwDeviceExtension,
  _Inout_ PSTOR_SLIST_HEADER SListHead
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param SListHead [in, out]

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.


## -returns



<b>StorPortInitializeSListHead</b> returns one of the following status codes:

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
The list head pointed to by <i>SListHead</i> was initialized successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer in <i>SListHead</i> is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



When allocated by the caller,  the <b>STOR_SLIST_HEADER</b> structure pointed to by <i>SListHead</i> must be aligned at  a <b>MEMORY_ALLOCATION_ALIGNMENT</b> boundary. <b>MEMORY_ALLOCATION_ALIGNMENT</b> is defined in <i>miniport.h</i>.

When memory for the list head is freed, any deallocation code must account for the original location of the buffer containing the list head structure prior to the adjustment for <b>MEMORY_ALLOCATION_ALIGNMENT</b>.




## -see-also

<a href="..\storport\nf-storport-storportinterlockedpopentryslist.md">StorPortInterlockedPopEntrySList</a>



<a href="..\storport\nf-storport-storportinterlockedflushslist.md">StorPortInterlockedFlushSList</a>



<a href="..\storport\nf-storport-storportinterlockedpushentryslist.md">StorPortInterlockedPushEntrySList</a>



<a href="..\storport\nf-storport-storportquerydepthslist.md">StorPortQueryDepthSList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeSListHead routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

