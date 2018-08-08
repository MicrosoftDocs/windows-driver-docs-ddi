---
UID: NS:ks._KSFILTER
title: "_KSFILTER"
author: windows-driver-content
description: The KSFILTER structure describes an instantiated filter.
old-location: stream\ksfilter.htm
tech.root: stream
ms.assetid: b9233f69-1ddf-4133-afd3-150aef5fc4a0
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSFILTER, KSFILTER, KSFILTER structure [Streaming Media Devices], PKSFILTER, PKSFILTER structure pointer [Streaming Media Devices], _KSFILTER, avstruct_6662a03a-c6de-4f5e-b86a-a3685dba320e.xml, ks/KSFILTER, ks/PKSFILTER, stream.ksfilter"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	ks.h
api_name:
-	KSFILTER
product:
- Windows
targetos: Windows
req.typenames: KSFILTER, *PKSFILTER
---

# _KSFILTER structure


## -description


The KSFILTER structure describes an instantiated filter.


## -struct-fields




### -field Descriptor

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a> structure that describes the characteristics of this particular filter.


### -field Bag

This member specifies the KSOBJECT_BAG (equivalent to type PVOID) associated with this filter instance. <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> are structures used to associate dynamic memory with a specific AVStream object. Anything in the filter object bag is automatically cleaned up when the filter is deleted.


### -field Context

A pointer that is used by the client to associate context information with the specific filter instance. Typically, such context information is associated in the filter's <b>Create</b> member as defined in the KSFILTER_DISPATCH table for this filter instance. Any dynamically allocated context information should be placed in the object bag with <a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>. <b>Context</b> is initialized to the value of the <b>Context</b> member of the parent <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> at the time the filter is created. See <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.


## -remarks



Drivers implementing software filters typically associate filter state with the KSFILTER structure. Software filters usually process data within the callback specified by the <b>Process</b> member of the corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a> structure.

Hardware filters typically do not use KSFILTER because the focus of the hardware driver is the platform transition: the movement of data between the host and the external hardware. This transition is typically handled by code associated with an AVStream queue object.

Also see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560941">KsAddItemToObjectBag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>
 

 

