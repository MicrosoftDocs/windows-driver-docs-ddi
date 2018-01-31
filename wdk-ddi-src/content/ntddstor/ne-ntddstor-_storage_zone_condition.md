---
UID: NE:ntddstor._STORAGE_ZONE_CONDITION
title: "_STORAGE_ZONE_CONDITION"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zone_condition.htm
old-project: storage
ms.assetid: 57FF3890-6B37-45EB-BB02-22B2ADDFAA90
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: STORAGE_ZONE_CONDITION enumeration [Storage Devices], ZoneConditionOffline, ntddstor/ZoneConditionOffline, storage.storage_zone_condition, ZoneConditionConventional, ZoneConditionImplicitlyOpened, ntddstor/ZoneConditionClosed, PSTORAGE_ZONE_CONDITION, ZoneConditionExplicitlyOpened, ntddstor/PSTORAGE_ZONE_CONDITION, _STORAGE_ZONE_CONDITION, PSTORAGE_ZONE_CONDITION enumeration pointer [Storage Devices], ntddstor/STORAGE_ZONE_CONDITION, ZoneConditionClosed, ZoneConditionFull, ZoneConditionEmpty, ntddstor/ZoneConditionExplicitlyOpened, *PSTORAGE_ZONE_CONDITION, ntddstor/ZoneConditionReadOnly, ZoneConditionReadOnly, STORAGE_ZONE_CONDITION, ntddstor/ZoneConditionEmpty, ntddstor/ZoneConditionImplicitlyOpened, ntddstor/ZoneConditionFull, ntddstor/ZoneConditionConventional
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
-	STORAGE_ZONE_CONDITION
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# _STORAGE_ZONE_CONDITION enumeration


## -description



<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>



## -syntax


````
typedef enum _STORAGE_ZONE_CONDITION { 
  ZoneConditionConventional      = 0x00,
  ZoneConditionEmpty             = 0x01,
  ZoneConditionImplicitlyOpened  = 0x02,
  ZoneConditionExplicitlyOpened  = 0x03,
  ZoneConditionClosed            = 0x04,
  ZoneConditionReadOnly          = 0x0D,
  ZoneConditionFull              = 0x0E,
  ZoneConditionOffline           = 0x0F
} STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION;
````


## -enum-fields




#### - ZoneConditionConventional

N/A


#### - ZoneConditionEmpty

N/A


#### - ZoneConditionImplicitlyOpened

N/A


#### - ZoneConditionExplicitlyOpened

N/A


#### - ZoneConditionClosed

N/A


#### - ZoneConditionReadOnly

N/A


#### - ZoneConditionFull

N/A


#### - ZoneConditionOffline

N/A

