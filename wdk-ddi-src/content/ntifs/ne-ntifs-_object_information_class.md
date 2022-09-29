---
UID: NE:ntifs._OBJECT_INFORMATION_CLASS
title: OBJECT_INFORMATION_CLASS (ntifs.h)
description: The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.
old-location: ifsk\object_information_class.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["OBJECT_INFORMATION_CLASS enumeration"]
ms.keywords: OBJECT_INFORMATION_CLASS, OBJECT_INFORMATION_CLASS enumeration [Installable File System Drivers], ObjectBasicInformation, ObjectTypeInformation, _OBJECT_INFORMATION_CLASS, ifsk.object_information_class, ntifs/OBJECT_INFORMATION_CLASS, ntifs/ObjectBasicInformation, ntifs/ObjectTypeInformation, objectstructures_60aa943f-6a91-429d-8c9d-1554f1bcf03e.xml
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: OBJECT_INFORMATION_CLASS
f1_keywords:
 - _OBJECT_INFORMATION_CLASS
 - ntifs/_OBJECT_INFORMATION_CLASS
 - OBJECT_INFORMATION_CLASS
 - ntifs/OBJECT_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _OBJECT_INFORMATION_CLASS
 - OBJECT_INFORMATION_CLASS
---

# OBJECT_INFORMATION_CLASS enumeration

## -description

The **OBJECT_INFORMATION_CLASS** enumeration type represents the type of information to supply about an object.

## -enum-fields

### -field ObjectBasicInformation

A [**PUBLIC_OBJECT_BASIC_INFORMATION**](ns-ntifs-_public_object_basic_information.md) structure is supplied.

### -field ObjectTypeInformation

A [**PUBLIC_OBJECT_TYPE_INFORMATION**](ns-ntifs-__public_object_type_information.md) structure is supplied.

## -see-also

[**PUBLIC_OBJECT_BASIC_INFORMATION**](ns-ntifs-_public_object_basic_information.md)

[**PUBLIC_OBJECT_TYPE_INFORMATION**](ns-ntifs-__public_object_type_information.md)

[**ZwQueryObject**](nf-ntifs-zwqueryobject.md)
