---
UID: NS:ks._KSFILTERFACTORY
title: _KSFILTERFACTORY (ks.h)
description: The KSFILTERFACTORY structure represents a filter factory.
old-location: stream\ksfilterfactory.htm
tech.root: stream
ms.assetid: c40e25f8-e6e5-43bc-895d-a6b247d07470
ms.date: 04/23/2018
ms.keywords: "*PKSFILTERFACTORY, KSFILTERFACTORY, KSFILTERFACTORY structure [Streaming Media Devices], PKSFILTERFACTORY, PKSFILTERFACTORY structure pointer [Streaming Media Devices], _KSFILTERFACTORY, avstruct_def7ad6b-4cda-4677-abbc-3f8a458fbc87.xml, ks/KSFILTERFACTORY, ks/PKSFILTERFACTORY, stream.ksfilterfactory"
ms.topic: struct
f1_keywords:
 - "ks/KSFILTERFACTORY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSFILTERFACTORY
product:
- Windows
targetos: Windows
req.typenames: KSFILTERFACTORY, *PKSFILTERFACTORY
---

# _KSFILTERFACTORY structure


## -description


The KSFILTERFACTORY structure represents a filter factory.


## -struct-fields




### -field FilterDescriptor

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure that describes the characteristics of filters created by this factory.


### -field Bag

This member specifies the KSOBJECT_BAG (equivalent to type PVOID) associated with this filter factory. Object bags are structures used to associate dynamic memory with a specific AVStream object. Anything in the filter factory object bag is automatically cleaned up when the filter factory is deleted. See the conceptual section on <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/object-bags">Object Bags</a> for more information.


### -field Context

A pointer to a memory address that the client may use to associate context information with the filter factory. AVStream does not use this member in any way. Note that any dynamic memory associated with the filter factory should be placed in the object bag with <b>KsAddItemToObjectBag</b>. <b>Context</b> is initialized to the value of the <b>Context</b> member of the parent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice">KSDEVICE</a> at the time the factory is created. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-object-hierarchy">AVStream Object Hierarchy</a>.


## -remarks



A filter factory explicitly represents a device's ability to instantiate a given type of filter as described by a filter descriptor.

Drivers for hardware typically use this structure to manage a particular function of the hardware that is exposed as a type of filter. Software filters generally do not need to manage the device at this level.

Filter factory objects are created in two ways. They can be created during the AddDevice processing as indicated by the device descriptor's list of filter descriptors. They can also be created explicitly by the client in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatefilterfactory">KsCreateFilterFactory</a>. The client may create filter factories at any time, but this is typically done during the processing of the PnP start IRP when an evaluation of assigned resources indicates what types of filters must be exposed by the device.

For the purposes of synchronization, the lifetime of filter factories created implicitly is defined as the interval starting when the client's device create dispatch function is (or would be) called and ending after the client's device PnP remove dispatch function is (or would be) called. The lifetime of filter factories created explicitly by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatefilterfactory">KsCreateFilterFactory</a> starts immediately after that call returns.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/object-bags">Object Bags</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatefilterfactory">KsCreateFilterFactory</a>
 

 

