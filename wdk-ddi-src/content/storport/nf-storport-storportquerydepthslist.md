---
UID: NF:storport.StorPortQueryDepthSList
title: StorPortQueryDepthSList function
author: windows-driver-content
description: Retrieves the number of entries in a Storport managed singly linked list.
old-location: storage\storportquerydepthslist.htm
old-project: storage
ms.assetid: 5E1CE999-8173-49B6-8CF7-F3A5B193A230
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortQueryDepthSList routine [Storage Devices], storport/StorPortQueryDepthSList, storage.storportquerydepthslist, StorPortQueryDepthSList
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	storport.h
apiname: 
-	StorPortQueryDepthSList
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortQueryDepthSList function


## -description


Retrieves the number of entries in a Storport managed singly linked list.


## -syntax


````
ULONG StorPortQueryDepthSList(
  _In_    PVOID              HwDeviceExtension,
  _Inout_ PSTOR_SLIST_HEADER SListHead,
  _Out_   PSHORT             Result
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param SListHead [in, out]

A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.


### -param Result [out]

A pointer to a <b>SHORT</b> value which receives the  list depth count.


## -returns


<b>StorPortQueryDepthSList</b> returns one of the following status codes:
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
The list depth  was successfully returned.

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


Since <b>StorPortQueryDepthSList</b> is not interlocked, the list  depth value pointed to by <i>Result</i> on return is not reliable in when multiple threads are operating on the list.



## -see-also

<a href="..\storport\nf-storport-storportinterlockedpushentryslist.md">StorPortInterlockedPushEntrySList</a>

<a href="..\storport\nf-storport-storportinitializeslisthead.md">StorPortInitializeSListHead</a>

<a href="..\storport\nf-storport-storportinterlockedflushslist.md">StorPortInterlockedFlushSList</a>

<a href="..\storport\nf-storport-storportinterlockedpopentryslist.md">StorPortInterlockedPopEntrySList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortQueryDepthSList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

