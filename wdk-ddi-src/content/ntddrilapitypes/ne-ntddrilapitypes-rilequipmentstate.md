---
UID: NE:ntddrilapitypes.RILEQUIPMENTSTATE
title: RILEQUIPMENTSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilequipmentstate.htm
old-project: netvista
ms.assetid: aa00ebc4-c8de-4a73-ad43-77f4e173e617
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilequipmentstate, RIL_EQSTATE_MAX, ntddrilapitypes/RIL_EQSTATE_MAX, RILEQUIPMENTSTATE, RILEQUIPMENTSTATE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_EQSTATE_SHUTDOWN, ntddrilapitypes/RIL_EQSTATE_FULL, RIL_EQSTATE_SHUTDOWN, RIL_EQSTATE_FULL, ntddrilapitypes/RILEQUIPMENTSTATE
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
-	RILEQUIPMENTSTATE
product: Windows
targetos: Windows
req.typenames: RILEQUIPMENTSTATE
---

# RILEQUIPMENTSTATE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILEQUIPMENTSTATE { 
  RIL_EQSTATE_FULL,
  RIL_EQSTATE_SHUTDOWN,
  RIL_EQSTATE_MAX
} RILEQUIPMENTSTATE;
````


## -enum-fields




### -field RIL_EQSTATE_MINIMUM


### -field RIL_EQSTATE_FULL


### -field RIL_EQSTATE_SHUTDOWN


### -field RIL_EQSTATE_MAX

