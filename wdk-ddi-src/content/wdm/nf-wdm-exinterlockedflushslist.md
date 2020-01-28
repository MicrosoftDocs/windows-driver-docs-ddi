---
UID: NF:wdm.ExInterlockedFlushSList
title: ExInterlockedFlushSList function (wdm.h)
description: The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list.
old-location: kernel\exinterlockedflushslist.htm
tech.root: kernel
ms.assetid: 98fcada7-5160-4eb2-ac7c-0ab1192340a9
ms.date: 04/30/2018
ms.keywords: ExInterlockedFlushSList, ExInterlockedFlushSList routine [Kernel-Mode Driver Architecture], k102_493935e2-44c7-471b-807f-ca6f110d8155.xml, kernel.exinterlockedflushslist, wdm/ExInterlockedFlushSList
f1_keywords:
 - "wdm/ExInterlockedFlushSList"
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExInterlockedFlushSList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedFlushSList macro


## -description


The <b>ExInterlockedFlushSList</b> routine atomically removes all entries from a sequenced singly linked list.


## -parameters




### -param ListHead

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.


## -remarks

If there were entries on the specified list, **ExInterlockedFlushSList** returns a pointer to the first [**SLIST_ENTRY**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_slist_entry) structure that was entry on the list; otherwise, it returns NULL.


<b>ExInterlockedFlushSList</b> does not delete the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_slist_entry">SLIST_ENTRY</a> structures that made up the list; it only sets the internal pointer of <i>ListHead</i> to the beginning of the list to <b>NULL</b>. The driver must free the entries explicitly.

The routine returns a pointer to the first <b>SLIST_ENTRY</b> structure that was on the list. The driver can use this pointer to iterate through the entries.

For more information about using this routine to implement a sequenced singly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.

Callers of <b>ExInterlockedFlushSList</b> can be running at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializeslisthead">ExInitializeSListHead</a>
 

 

