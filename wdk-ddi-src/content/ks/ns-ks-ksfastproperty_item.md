---
UID: NS:ks.KSFASTPROPERTY_ITEM
title: KSFASTPROPERTY_ITEM
author: windows-driver-content
description: The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching.
old-location: stream\ksfastproperty_item.htm
old-project: stream
ms.assetid: 8a39b7cb-cd05-4fb8-9e50-7425e689a36f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSFASTPROPERTY_ITEM, KSFASTPROPERTY_ITEM, KSFASTPROPERTY_ITEM structure [Streaming Media Devices], PKSFASTPROPERTY_ITEM, PKSFASTPROPERTY_ITEM structure pointer [Streaming Media Devices], ks-struct_dddb648f-ea8a-436a-b948-397364fe2db6.xml, ks/KSFASTPROPERTY_ITEM, ks/PKSFASTPROPERTY_ITEM, stream.ksfastproperty_item"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSFASTPROPERTY_ITEM
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


### -field Reserved

Reserved and set to zero.


#### - GetPropertyHandler

Points to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567173">KStrFastHandler</a> routine that specifies the fast handler for retrieving the property. If this is <b>NULL</b>, the property cannot be read with a fast handler.


#### - GetSupported

A boolean value that indicates if the driver has supplied a get property handler.


#### - SetPropertyHandler

Points to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567173">KStrFastHandler</a> routine that specifies the fast handler for setting the property. If this is <b>NULL</b>, the property cannot be set with a fast handler.


#### - SetSupported

A boolean value that indicates if the driver has supplied a set property handler.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567173">KStrFastHandler</a>
 

 

