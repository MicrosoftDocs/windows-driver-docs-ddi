---
UID: NE:rilapitypes.RILEMERGENCYNUMBERCATEGORY
title: RILEMERGENCYNUMBERCATEGORY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumbercategory.htm
old-project: netvista
ms.assetid: f1ad9a15-70c8-4331-b350-f681aa216aaf
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILEMERGENCYNUMBERCATEGORY, RILEMERGENCYNUMBERCATEGORY enumeration [Network Drivers Starting with Windows Vista], RIL_ENUM_ALL, RIL_ENUM_AMBULANCE, RIL_ENUM_AUTO_ECALL, RIL_ENUM_FIRE_BRIGADE, RIL_ENUM_MANUAL_ECALL, RIL_ENUM_MARINE_GUARD, RIL_ENUM_MOUNTAIN_RESCUE, netvista.rilemergencynumbercategory, ntddrilapitypes/RILEMERGENCYNUMBERCATEGORY, ntddrilapitypes/RIL_ENUM_ALL, ntddrilapitypes/RIL_ENUM_AMBULANCE, ntddrilapitypes/RIL_ENUM_AUTO_ECALL, ntddrilapitypes/RIL_ENUM_FIRE_BRIGADE, ntddrilapitypes/RIL_ENUM_MANUAL_ECALL, ntddrilapitypes/RIL_ENUM_MARINE_GUARD, ntddrilapitypes/RIL_ENUM_MOUNTAIN_RESCUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILEMERGENCYNUMBERCATEGORY
product: Windows
targetos: Windows
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




### -field RIL_ENUM_POLICE


### -field RIL_ENUM_AMBULANCE


### -field RIL_ENUM_FIRE_BRIGADE


### -field RIL_ENUM_MARINE_GUARD


### -field RIL_ENUM_MOUNTAIN_RESCUE


### -field RIL_ENUM_MANUAL_ECALL


### -field RIL_ENUM_AUTO_ECALL


### -field RIL_ENUM_ALL

