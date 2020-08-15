---
UID: NF:wdfchildlist.WDF_CHILD_LIST_ITERATOR_INIT
title: WDF_CHILD_LIST_ITERATOR_INIT function (wdfchildlist.h)
description: The WDF_CHILD_LIST_ITERATOR_INIT function initializes a WDF_CHILD_LIST_ITERATOR structure.
old-location: wdf\wdf_child_list_iterator_init.htm
tech.root: wdf
ms.assetid: e06a377a-e68a-4773-9f7f-b1c47010029c
ms.date: 02/26/2018
keywords: ["WDF_CHILD_LIST_ITERATOR_INIT function"]
ms.keywords: DFDeviceObjectChildListRef_5040aac1-503f-4559-ad77-0304bfb67e3d.xml, WDF_CHILD_LIST_ITERATOR_INIT, WDF_CHILD_LIST_ITERATOR_INIT function, kmdf.wdf_child_list_iterator_init, wdf.wdf_child_list_iterator_init, wdfchildlist/WDF_CHILD_LIST_ITERATOR_INIT
f1_keywords:
 - "wdfchildlist/WDF_CHILD_LIST_ITERATOR_INIT"
 - "WDF_CHILD_LIST_ITERATOR_INIT"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdfchildlist.h
api_name:
- WDF_CHILD_LIST_ITERATOR_INIT
targetos: Windows
req.typenames: 
---

# WDF_CHILD_LIST_ITERATOR_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_LIST_ITERATOR_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure.


## -parameters




### -param Iterator 
[out]
A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure.


### -param Flags 
[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flag value.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>
 

 

