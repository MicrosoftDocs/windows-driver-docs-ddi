---
UID: NS:ks.__unnamed_struct_67
title: KSFASTPROPERTY_ITEM (ks.h)
description: The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching.
old-location: stream\ksfastproperty_item.htm
tech.root: stream
ms.assetid: 8a39b7cb-cd05-4fb8-9e50-7425e689a36f
ms.date: 04/23/2018
ms.keywords: "*PKSFASTPROPERTY_ITEM, KSFASTPROPERTY_ITEM, KSFASTPROPERTY_ITEM structure [Streaming Media Devices], PKSFASTPROPERTY_ITEM, PKSFASTPROPERTY_ITEM structure pointer [Streaming Media Devices], ks-struct_dddb648f-ea8a-436a-b948-397364fe2db6.xml, ks/KSFASTPROPERTY_ITEM, ks/PKSFASTPROPERTY_ITEM, stream.ksfastproperty_item"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
- ks.h
api_name:
- KSFASTPROPERTY_ITEM
product:
- Windows
targetos: Windows
req.typenames: KSFASTPROPERTY_ITEM, *PKSFASTPROPERTY_ITEM
---

# KSFASTPROPERTY_ITEM structure


## -description


The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching.


## -struct-fields




### -field PropertyId

Specifies the identifier of the specific property within the set.


### -field GetPropertyHandler

Points to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfasthandler">KStrFastHandler</a> routine that specifies the fast handler for retrieving the property. If this is <b>NULL</b>, the property cannot be read with a fast handler.


### -field GetSupported

A boolean value that indicates if the driver has supplied a get property handler.


### -field SetPropertyHandler

Points to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfasthandler">KStrFastHandler</a> routine that specifies the fast handler for setting the property. If this is <b>NULL</b>, the property cannot be set with a fast handler.


### -field SetSupported

A boolean value that indicates if the driver has supplied a set property handler.


### -field Reserved

Reserved and set to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfasthandler">KStrFastHandler</a>
 

 

