---
UID: NF:storport.StorPortInitializeListHead
title: StorPortInitializeListHead function (storport.h)
description: The StorPortInitializeListHead routine initializes a STOR_LIST_ENTRY structure that represents the head of a doubly linked list.
old-location: storage\storportinitializelisthead.htm
tech.root: storage
ms.assetid: E37C54C1-209F-4944-940B-2247E86C8130
ms.date: 03/29/2018
ms.keywords: StorPortInitializeListHead, StorPortInitializeListHead routine [Storage Devices], storage.storportinitializelisthead, storport/StorPortInitializeListHead
ms.topic: function
f1_keywords:
 - "storport/StorPortInitializeListHead"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortInitializeListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitializeListHead function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInitializeListHead</b> routine initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_list_entry">STOR_LIST_ENTRY</a> structure that represents the head of a doubly linked list.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ListHead [out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_list_entry">STOR_LIST_ENTRY</a> structure that represents the head of the list.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-initializelisthead">InitializeListHead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedinsertheadlist">StorPortInterlockedInsertHeadList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedinserttaillist">StorPortInterlockedInsertTailList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinterlockedremoveheadlist">StorPortInterlockedRemoveHeadList</a>
 

 

