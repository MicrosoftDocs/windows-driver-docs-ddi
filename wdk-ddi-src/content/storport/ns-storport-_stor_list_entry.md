---
UID: NS:storport._STOR_LIST_ENTRY
title: _STOR_LIST_ENTRY (storport.h)
description: A STOR_LIST_ENTRY structure describes an entry in a doubly linked list or serves as the header for such a list.
old-location: storage\stor_list_entry.htm
tech.root: storage
ms.assetid: 41E713D9-9499-40EB-8B21-DDB73362BAE3
ms.date: 03/29/2018
ms.keywords: "*PSTOR_LIST_ENTRY, PSTOR_LIST_ENTRY, PSTOR_LIST_ENTRY structure pointer [Storage Devices], STOR_LIST_ENTRY, STOR_LIST_ENTRY structure [Storage Devices], _STOR_LIST_ENTRY, storage.stor_list_entry, storport/PSTOR_LIST_ENTRY, storport/STOR_LIST_ENTRY"
ms.topic: struct
f1_keywords:
 - "storport/STOR_LIST_ENTRY"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- STOR_LIST_ENTRY
product:
- Windows
targetos: Windows
req.typenames: STOR_LIST_ENTRY, *PSTOR_LIST_ENTRY
---

# _STOR_LIST_ENTRY structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

A <b>STOR_LIST_ENTRY</b> structure describes an entry in a doubly linked list or serves as the header for such a list.


## -struct-fields




### -field Flink

For a <b>LIST_ENTRY</b> structure that serves as a list entry, the <b>Flink</b> member points to the next entry in the list or to the list header if there is no next entry in the list. 

For a <b>LIST_ENTRY</b> structure that serves as the list header, the <b>Flink</b> member points to the first entry in the list or to the LIST_ENTRY structure itself if the list is empty.


### -field Blink

For a <b>LIST_ENTRY</b> structure that serves as a list entry, the <b>Blink</b> member points to the previous entry in the list or to the list header if there is no previous entry in the list.

For a <b>LIST_ENTRY</b> structure that serves as the list header, the <b>Blink</b> member points to the last entry in the list or to the <b>LIST_ENTRY</b> structure itself if the list is empty.


## -remarks



A <b>STOR_LIST_ENTRY</b> structure that describes the list head must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitializelisthead">StorPortInitializeListHead
</a>.

A driver can access the <b>Flink</b> or <b>Blink</b> members of a <b>STOR_LIST_ENTRY</b>, but the members must only be updated by the system routines supplied for this purpose.

For more information about how to use <b>STOR_LIST_ENTRY</b> structures to implement a doubly linked list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/singly-and-doubly-linked-lists">Singly and Doubly Linked Lists</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-insertheadlist">InsertHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-inserttaillist">InsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-islistempty">IsListEmpty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-removeentrylist">RemoveEntryList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-removeheadlist">RemoveHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-removetaillist">RemoveTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinterlockedinsertheadlist">StorPortInterlockedInsertHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinterlockedinserttaillist">StorPortInterlockedInsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinterlockedremoveheadlist">StorPortInterlockedRemoveHeadList</a>
 

 

