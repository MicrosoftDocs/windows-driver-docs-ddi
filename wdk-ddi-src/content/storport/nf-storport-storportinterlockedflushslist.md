---
UID: NF:storport.StorPortInterlockedFlushSList
title: StorPortInterlockedFlushSList function (storport.h)
description: Removes all items from a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system.
old-location: storage\storportinterlockedflushslist.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortInterlockedFlushSList function"]
ms.keywords: StorPortInterlockedFlushSList, StorPortInterlockedFlushSList routine [Storage Devices], storage.storportinterlockedflushslist, storport/StorPortInterlockedFlushSList
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortInterlockedFlushSList
 - storport/StorPortInterlockedFlushSList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortInterlockedFlushSList
---

# StorPortInterlockedFlushSList function


## -description

Removes all items from a Storport managed singly linked list. Access to the list is synchronized on a multiprocessor system

## -parameters

### -param HwDeviceExtension [in]


A pointer to the hardware device extension for the host bus adapter (HBA).

### -param SListHead [in, out]


A pointer to an <b>STOR_SLIST_HEADER</b> structure that represents the head of a singly linked list. This structure is considered opaque and is for use by the Storport driver only.

### -param Result [out]


A pointer to a list entry pointer. The value returned is a pointer to  the items removed from the list. If the list is empty, then <b>NULL</b> is returned in value pointed to by <i>Result</i>.

## -returns

<b>StorPortInterlockedFlushSList</b> returns one of the following status codes:

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
A pointer in <i>SListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table>

## -remarks

The <b>StorPortInterlockedFlushSList</b> will also return <b>STATUS_SUCCESS</b> when no entries are in the list. The pointer value referenced by <i>Result</i> must be evaluated for <b>NULL</b> to verify that no entries were returned.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeslisthead">StorPortInitializeSListHead</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedpopentryslist">StorPortInterlockedPopEntrySList</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedpushentryslist">StorPortInterlockedPushEntrySList</a>



<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportquerydepthslist">StorPortQueryDepthSList</a>
