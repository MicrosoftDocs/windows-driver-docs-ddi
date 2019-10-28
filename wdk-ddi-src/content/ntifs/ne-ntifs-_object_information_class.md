---
UID: NE:ntifs._OBJECT_INFORMATION_CLASS
title: _OBJECT_INFORMATION_CLASS (ntifs.h)
description: The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.
old-location: ifsk\object_information_class.htm
tech.root: ifsk
ms.assetid: fbcca01d-2dd6-405a-9ec2-709652e9dcd6
ms.date: 04/16/2018
ms.keywords: OBJECT_INFORMATION_CLASS, OBJECT_INFORMATION_CLASS enumeration [Installable File System Drivers], ObjectBasicInformation, ObjectTypeInformation, _OBJECT_INFORMATION_CLASS, ifsk.object_information_class, ntifs/OBJECT_INFORMATION_CLASS, ntifs/ObjectBasicInformation, ntifs/ObjectTypeInformation, objectstructures_60aa943f-6a91-429d-8c9d-1554f1bcf03e.xml
ms.topic: enum
f1_keywords:
 - "ntifs/OBJECT_INFORMATION_CLASS"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Microsoft Windows 2000.
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
- ntifs.h
api_name:
- OBJECT_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: OBJECT_INFORMATION_CLASS
---

# _OBJECT_INFORMATION_CLASS enumeration


## -description


The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object.


## -enum-fields




### -field ObjectBasicInformation

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_public_object_basic_information">PUBLIC_OBJECT_BASIC_INFORMATION</a> structure is supplied.


### -field ObjectTypeInformation

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-__public_object_type_information">PUBLIC_OBJECT_TYPE_INFORMATION</a> structure is supplied.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_public_object_basic_information">PUBLIC_OBJECT_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-__public_object_type_information">PUBLIC_OBJECT_TYPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567062">ZwQueryObject</a>
 

 

