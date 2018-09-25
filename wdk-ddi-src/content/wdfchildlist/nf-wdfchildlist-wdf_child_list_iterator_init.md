---
UID: NF:wdfchildlist.WDF_CHILD_LIST_ITERATOR_INIT
title: WDF_CHILD_LIST_ITERATOR_INIT function
author: windows-driver-content
description: The WDF_CHILD_LIST_ITERATOR_INIT function initializes a WDF_CHILD_LIST_ITERATOR structure.
old-location: wdf\wdf_child_list_iterator_init.htm
tech.root: wdf
ms.assetid: e06a377a-e68a-4773-9f7f-b1c47010029c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_5040aac1-503f-4559-ad77-0304bfb67e3d.xml, WDF_CHILD_LIST_ITERATOR_INIT, WDF_CHILD_LIST_ITERATOR_INIT function, kmdf.wdf_child_list_iterator_init, wdf.wdf_child_list_iterator_init, wdfchildlist/WDF_CHILD_LIST_ITERATOR_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfchildlist.h
api_name:
-	WDF_CHILD_LIST_ITERATOR_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_CHILD_LIST_ITERATOR_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_LIST_ITERATOR_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a> structure.


## -parameters




### -param Iterator [out]

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a> structure.


### -param Flags [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552507">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flag value.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552507">WDF_RETRIEVE_CHILD_FLAGS</a>
 

 

