---
UID: NE:ntifs._OBJECT_INFORMATION_CLASS
title: OBJECT_INFORMATION_CLASS (ntifs.h)
description: The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.
tech.root: ifsk
ms.date: 05/05/2025
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

The **OBJECT_INFORMATION_CLASS** enumeration type represents the type of information to supply about a kernel object.

## -enum-fields

### -field ObjectBasicInformation:0

The caller-allocated buffer passed to [**ZwQueryObject**](nf-ntifs-zwqueryobject.md) in the buffer that **ObjectInformation** points to contains a [**PUBLIC_OBJECT_BASIC_INFORMATION**](ns-ntifs-_public_object_basic_information.md) structure.

### -field ObjectTypeInformation:2

The caller-allocated buffer passed to [**ZwQueryObject**](nf-ntifs-zwqueryobject.md) in the buffer that **ObjectInformation** points to contains a  [**PUBLIC_OBJECT_TYPE_INFORMATION**](ns-ntifs-__public_object_type_information.md) structure.

## -see-also

[**PUBLIC_OBJECT_BASIC_INFORMATION**](ns-ntifs-_public_object_basic_information.md)

[**PUBLIC_OBJECT_TYPE_INFORMATION**](ns-ntifs-__public_object_type_information.md)

[**ZwQueryObject**](nf-ntifs-zwqueryobject.md)
