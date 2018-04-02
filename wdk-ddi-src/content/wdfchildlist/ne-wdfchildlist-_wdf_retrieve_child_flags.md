---
UID: NE:wdfchildlist._WDF_RETRIEVE_CHILD_FLAGS
title: "_WDF_RETRIEVE_CHILD_FLAGS"
author: windows-driver-content
description: The WDF_RETRIEVE_CHILD_FLAGS enumeration defines flags that a driver can set before calling WdfChildListBeginIteration.
old-location: wdf\wdf_retrieve_child_flags.htm
old-project: wdf
ms.assetid: 43294943-cc73-45d4-8e0b-e7d29420bb7e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_f82096f7-f6f9-4e49-a3e3-2641f60f98d9.xml, WDF_RETRIEVE_CHILD_FLAGS, WDF_RETRIEVE_CHILD_FLAGS enumeration, WdfRetrieveAddedChildren, WdfRetrieveAllChildren, WdfRetrieveMissingChildren, WdfRetrievePendingChildren, WdfRetrievePresentChildren, WdfRetrieveUnspecified, _WDF_RETRIEVE_CHILD_FLAGS, kmdf.wdf_retrieve_child_flags, wdf.wdf_retrieve_child_flags, wdfchildlist/WDF_RETRIEVE_CHILD_FLAGS, wdfchildlist/WdfRetrieveAddedChildren, wdfchildlist/WdfRetrieveAllChildren, wdfchildlist/WdfRetrieveMissingChildren, wdfchildlist/WdfRetrievePendingChildren, wdfchildlist/WdfRetrievePresentChildren, wdfchildlist/WdfRetrieveUnspecified
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_RETRIEVE_CHILD_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# _WDF_RETRIEVE_CHILD_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_RETRIEVE_CHILD_FLAGS</b> enumeration defines flags that a driver can set before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a>.


## -enum-fields




### -field WdfRetrieveUnspecified

Reserved for internal use only.


### -field WdfRetrievePresentChildren

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> will retrieve child devices for which a framework device object exists.


### -field WdfRetrieveMissingChildren

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are marked as missing. 


### -field WdfRetrievePendingChildren

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> will retrieve child devices that the driver has reported as present, but for which a framework device object has not been created (because the framework has not called the driver's <a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a> callback function). 


### -field WdfRetrieveAddedChildren

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are present or pending.


### -field WdfRetrieveAllChildren

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> will retrieve child devices that are present, pending, or missing.


## -remarks



Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a>, your driver must set <b>WDF_RETRIEVE_CHILD_FLAGS</b>-typed flags in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551230">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545601">WdfChildListBeginIteration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>
 

 

