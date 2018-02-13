---
UID: NE:ntddstor._STORAGE_ZONES_ATTRIBUTES
title: "_STORAGE_ZONES_ATTRIBUTES"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zones_attributes.htm
old-project: storage
ms.assetid: 6C86A931-C87C-4273-9409-A45A3FDB8B4C
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PSTORAGE_ZONES_ATTRIBUTES, ntddstor/PSTORAGE_ZONES_ATTRIBUTES, ntddstor/STORAGE_ZONES_ATTRIBUTES, storage.storage_zones_attributes, PSTORAGE_ZONES_ATTRIBUTES enumeration pointer [Storage Devices], ntddstor/ZonesAttributeTypeAndLengthMayDifferent, ZonesAttributeTypeMayDifferentLengthSame, ZonesAttributeTypeSameLastZoneLengthDifferent, _STORAGE_ZONES_ATTRIBUTES, PSTORAGE_ZONES_ATTRIBUTES, ntddstor/ZonesAttributeTypeSameLastZoneLengthDifferent, ntddstor/ZonesAttributeTypeMayDifferentLengthSame, STORAGE_ZONES_ATTRIBUTES, ZonesAttributeTypeAndLengthMayDifferent, ntddstor/ZonesAttributeTypeSameLengthSame, STORAGE_ZONES_ATTRIBUTES enumeration [Storage Devices], ZonesAttributeTypeSameLengthSame"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	STORAGE_ZONES_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONES_ATTRIBUTES, STORAGE_ZONES_ATTRIBUTES"
---

# _STORAGE_ZONES_ATTRIBUTES enumeration


## -description



<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax


````
typedef enum _STORAGE_ZONES_ATTRIBUTES { 
  ZonesAttributeTypeAndLengthMayDifferent        = 0,
  ZonesAttributeTypeSameLengthSame               = 1,
  ZonesAttributeTypeSameLastZoneLengthDifferent  = 2,
  ZonesAttributeTypeMayDifferentLengthSame       = 3
} STORAGE_ZONES_ATTRIBUTES, *PSTORAGE_ZONES_ATTRIBUTES;
````


## -enum-fields




### -field ZonesAttributeTypeAndLengthMayDifferent

N/A


### -field ZonesAttributeTypeSameLengthSame

N/A


### -field ZonesAttributeTypeSameLastZoneLengthDifferent

N/A


### -field ZonesAttributeTypeMayDifferentLengthSame

N/A

