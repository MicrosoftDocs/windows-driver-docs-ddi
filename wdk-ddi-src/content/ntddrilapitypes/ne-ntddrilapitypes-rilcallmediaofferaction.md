---
UID: NE:ntddrilapitypes.RILCALLMEDIAOFFERACTION
title: RILCALLMEDIAOFFERACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferaction.htm
old-project: netvista
ms.assetid: 0a2ac234-633d-4ebc-9e13-05a12534f93a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLMEDIAOFFERACTION_ASK, RIL_CALLMEDIAOFFERACTION_MAX, RIL_CALLMEDIAOFFERACTION_ERROR, ntddrilapitypes/RILCALLMEDIAOFFERACTION, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_REJECT, RILCALLMEDIAOFFERACTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIAOFFERACTION_ACCEPT, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_MAX, netvista.rilcallmediaofferaction, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ACCEPT, RIL_CALLMEDIAOFFERACTION_REJECT, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ASK, RIL_CALLMEDIAOFFERACTION_CANCEL, RILCALLMEDIAOFFERACTION, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_CANCEL, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ERROR
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
-	RILCALLMEDIAOFFERACTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERACTION
---

# RILCALLMEDIAOFFERACTION enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLMEDIAOFFERACTION { 
  RIL_CALLMEDIAOFFERACTION_ERROR,
  RIL_CALLMEDIAOFFERACTION_REJECT,
  RIL_CALLMEDIAOFFERACTION_ASK,
  RIL_CALLMEDIAOFFERACTION_ACCEPT,
  RIL_CALLMEDIAOFFERACTION_CANCEL,
  RIL_CALLMEDIAOFFERACTION_MAX
} RILCALLMEDIAOFFERACTION;
````


## -enum-fields




### -field RIL_CALLMEDIAOFFERACTION_NONE



#### - RIL_CALLMEDIAOFFERACTION_ERROR



#### - RIL_CALLMEDIAOFFERACTION_REJECT



#### - RIL_CALLMEDIAOFFERACTION_ASK



#### - RIL_CALLMEDIAOFFERACTION_ACCEPT



#### - RIL_CALLMEDIAOFFERACTION_CANCEL



#### - RIL_CALLMEDIAOFFERACTION_MAX


