---
UID: NF:wiautil.CWiauPropertyList.SetAccessSubType(INT,ULONG,ULONG)
title: CWiauPropertyList::SetAccessSubType(INT,ULONG,ULONG)
author: windows-driver-content
description: The CWiauPropertyList::SetAccessSubType(INT,ULONG,ULONG) method resets a property's access and subtype.
old-location: image\cwiaupropertylist_setaccesssubtype.htm
tech.root: image
ms.assetid: 207125d3-0833-4c5d-b66f-aa49c96a6a2d
ms.author: windowsdriverdev
ms.date: 9/7/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetAccessSubType method, CWiauPropertyList.SetAccessSubType, CWiauPropertyList.SetAccessSubType(INT,ULONG,ULONG), CWiauPropertyList::SetAccessSubType, CWiauPropertyList::SetAccessSubType(INT,ULONG,ULONG), SetAccessSubType, SetAccessSubType method [Imaging Devices], SetAccessSubType method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setaccesssubtype, wiauFncs_ab4b792f-54f0-4efa-bb13-5b71d94e03e0.xml, wiautil/CWiauPropertyList::SetAccessSubType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
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
-	COM
api_location:
-	Wiautil.h
api_name:
-	CWiauPropertyList.SetAccessSubType
product:
-	Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList::SetAccessSubType(INT,ULONG,ULONG)

## -description

The **CWiauPropertyList::SetAccessSubType(INT,ULONG,ULONG)** method resets a property's access and subtype. 

## -parameters

### -param index

Specifies the property's index in the property list.

### -param Access

Specifies the type of access for the property, usually either WIA_PROP_READ (read-only) or WIA_PROP_RW (read/write).

### -param SubType

Specifies the property subtype, one of WIA_PROP_FLAG, WIA_PROP_LIST, WIA_PROP_RANGE, or WIA_PROP_NONE. The first three constants indicate, respectively, that a property is a set of flag values, a list of values, or a range of values. The fourth constant indicates that a property is none of these.

## -returns

This method does not return a value.

## -remarks

A property's access and subtype are set originally in a call to the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)
