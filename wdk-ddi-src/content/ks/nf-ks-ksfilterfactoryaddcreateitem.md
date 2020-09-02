---
UID: NF:ks.KsFilterFactoryAddCreateItem
title: KsFilterFactoryAddCreateItem function (ks.h)
description: The KsFilterFactoryAddCreateItem function adds a new create item for the specified filter factory.
old-location: stream\ksfilterfactoryaddcreateitem.htm
tech.root: stream
ms.assetid: c09840fb-8195-4ac5-a164-ba4d82615344
ms.date: 04/23/2018
keywords: ["KsFilterFactoryAddCreateItem function"]
ms.keywords: KsFilterFactoryAddCreateItem, KsFilterFactoryAddCreateItem function [Streaming Media Devices], avfunc_f4a42084-1d8f-49f8-a6d3-d09304e11049.xml, ks/KsFilterFactoryAddCreateItem, stream.ksfilterfactoryaddcreateitem
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterFactoryAddCreateItem
 - ks/KsFilterFactoryAddCreateItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterFactoryAddCreateItem
---

# KsFilterFactoryAddCreateItem function


## -description

The<b> KsFilterFactoryAddCreateItem</b> function adds a new create item for the specified filter factory.

## -parameters

### -param FilterFactory 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a> structure representing the filter factory to which to add a new create item.

### -param RefString 

[in]
A pointer to a Unicode text string that identifies the create item.

### -param SecurityDescriptor 

[in, optional]
This parameter optionally contains a pointer to a SECURITY_DESCRIPTOR structure for this type of object. See the Microsoft Windows SDK For information about this structure. For related information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a>. If <b>NULL</b>, no descriptor is assigned.

### -param CreateItemFlags 

[in]
See the table for the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a>.

## -returns

<b>KsFilterFactoryAddCreateItem</b> returns success or failure of the attempt to add a new create item.

## -remarks

Normally, only a single create item using the reference GUID supplied in the filter descriptor is added for the filter factory. This function allows the caller to add create items associated with the given filter factory.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/initializing-an-avstream-minidriver">Initializing an AVStream Minidriver</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksobject_create_item">KSOBJECT_CREATE_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksaddobjectcreateitemtodeviceheader">KsAddObjectCreateItemToDeviceHeader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksaddobjectcreateitemtoobjectheader">KsAddObjectCreateItemToObjectHeader</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectcreateitem">KsAllocateObjectCreateItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfreeobjectcreateitem">KsFreeObjectCreateItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksqueryobjectcreateitem">KsQueryObjectCreateItem</a>

