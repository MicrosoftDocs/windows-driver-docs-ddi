---
UID: NE:ntddrilapitypes.RILEMERGENCYNUMBERCATEGORY
title: RILEMERGENCYNUMBERCATEGORY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumbercategory.htm
old-project: netvista
ms.assetid: f1ad9a15-70c8-4331-b350-f681aa216aaf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilemergencynumbercategory, ntddrilapitypes/RIL_ENUM_FIRE_BRIGADE, ntddrilapitypes/RIL_ENUM_MANUAL_ECALL, RIL_ENUM_MARINE_GUARD, ntddrilapitypes/RIL_ENUM_MOUNTAIN_RESCUE, ntddrilapitypes/RIL_ENUM_MARINE_GUARD, RIL_ENUM_AUTO_ECALL, RILEMERGENCYNUMBERCATEGORY, ntddrilapitypes/RIL_ENUM_ALL, RIL_ENUM_MANUAL_ECALL, RIL_ENUM_AMBULANCE, ntddrilapitypes/RIL_ENUM_AUTO_ECALL, RILEMERGENCYNUMBERCATEGORY enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILEMERGENCYNUMBERCATEGORY, RIL_ENUM_FIRE_BRIGADE, RIL_ENUM_ALL, RIL_ENUM_MOUNTAIN_RESCUE, ntddrilapitypes/RIL_ENUM_AMBULANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILEMERGENCYNUMBERCATEGORY
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYNUMBERCATEGORY
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



#### - RIL_ENUM_AMBULANCE



#### - RIL_ENUM_FIRE_BRIGADE



#### - RIL_ENUM_MARINE_GUARD



#### - RIL_ENUM_MOUNTAIN_RESCUE



#### - RIL_ENUM_MANUAL_ECALL



#### - RIL_ENUM_AUTO_ECALL



#### - RIL_ENUM_ALL


