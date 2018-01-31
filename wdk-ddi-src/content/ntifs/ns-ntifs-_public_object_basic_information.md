---
UID: NS:ntifs._PUBLIC_OBJECT_BASIC_INFORMATION
title: "_PUBLIC_OBJECT_BASIC_INFORMATION"
author: windows-driver-content
description: The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.
old-location: ifsk\public_object_basic_information.htm
old-project: ifsk
ms.assetid: 2190f88e-6905-4e58-9523-2b6d4864c776
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PPUBLIC_OBJECT_BASIC_INFORMATION, PPUBLIC_OBJECT_BASIC_INFORMATION structure pointer [Installable File System Drivers], *PPUBLIC_OBJECT_BASIC_INFORMATION, PUBLIC_OBJECT_BASIC_INFORMATION, objectstructures_f0dec604-d95c-47b4-aedc-168a3ae1dedc.xml, ifsk.public_object_basic_information, ntifs/PUBLIC_OBJECT_BASIC_INFORMATION, PUBLIC_OBJECT_BASIC_INFORMATION structure [Installable File System Drivers], ntifs/PPUBLIC_OBJECT_BASIC_INFORMATION, _PUBLIC_OBJECT_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Microsoft Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	PUBLIC_OBJECT_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_BASIC_INFORMATION, *PPUBLIC_OBJECT_BASIC_INFORMATION
---

# _PUBLIC_OBJECT_BASIC_INFORMATION structure


## -description


The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object.


## -syntax


````
typedef struct _PUBLIC_OBJECT_BASIC_INFORMATION {
  ULONG       Attributes;
  ACCESS_MASK GrantedAccess;
  ULONG       HandleCount;
  ULONG       PointerCount;
  ULONG       Reserved[10];
} PUBLIC_OBJECT_BASIC_INFORMATION, *PPUBLIC_OBJECT_BASIC_INFORMATION;
````


## -struct-fields




#### - Attributes

Specifies the attributes of the object.


#### - GrantedAccess

Specifies a mask that represents the granted access to the object.


#### - HandleCount

Specifies the number of handles to the object.


#### - PointerCount

Specifies the number of pointers at an object.


#### - Reserved

Reserved for system use.

