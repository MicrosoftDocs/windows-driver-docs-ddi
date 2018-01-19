---
UID: NE:rilapitypes.RILEMERGENCYNUMBERCATEGORY
title: RILEMERGENCYNUMBERCATEGORY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumbercategory_2.htm
old-project: netvista
ms.assetid: 322e2622-1f9a-433a-8fe9-9d59c00ce8be
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILEMERGENCYNUMBERCATEGORY, RILEMERGENCYNUMBERCATEGORY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILEMERGENCYNUMBERCATEGORY
req.alt-loc: rilapitypes.h
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
req.typenames: RILEMERGENCYNUMBERCATEGORY
req.product: Windows 10 or later.
---

# RILEMERGENCYNUMBERCATEGORY enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILEMERGENCYNUMBERCATEGORY { 
  RIL_ENUM_AMBULANCE,
  RIL_ENUM_FIRE_BRIGADE,
  RIL_ENUM_MARINE_GUARD,
  RIL_ENUM_MOUNTAIN_RESCUE,
  RIL_ENUM_MANUAL_ECALL,
  RIL_ENUM_AUTO_ECALL,
  RIL_ENUM_ALL
} RILEMERGENCYNUMBERCATEGORY;
````


## -enum-fields

### -field RIL_ENUM_AMBULANCE


### -field RIL_ENUM_FIRE_BRIGADE


### -field RIL_ENUM_MARINE_GUARD


### -field RIL_ENUM_MOUNTAIN_RESCUE


### -field RIL_ENUM_MANUAL_ECALL


### -field RIL_ENUM_AUTO_ECALL


### -field RIL_ENUM_ALL


## -remarks
